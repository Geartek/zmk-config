# Copyright (c) 2020 The ZMK Contributors
#
# SPDX-License-Identifier: MIT

# Custom OLED status screen (adds an idle/typing "bongo cat" animation
# alongside the standard battery/output/layer/wpm widgets). Only built when
# CONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM=y (see config/corne.conf).
target_sources_ifdef(CONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM app PRIVATE
    src/status_screen.c
    src/widgets/bongo_cat.c
    src/widgets/bongo_cat_images.c
)
