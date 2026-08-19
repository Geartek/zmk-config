# Copyright (c) 2020 The ZMK Contributors
#
# SPDX-License-Identifier: MIT

# Custom OLED status screen (battery/output/layer/wpm widgets, same layout
# as the built-in screen). Only built when CONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM=y
# (see config/corne.conf).
target_sources_ifdef(CONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM app PRIVATE
    src/status_screen.c
)

# src/widgets/bongo_cat*.c (an idle/typing cat animation) is not currently
# wired into status_screen.c: it reliably hard-faults the central half at
# boot (reproducible reboot loop), root cause not yet found. Left out of the
# build until that's debugged with proper crash logging.
