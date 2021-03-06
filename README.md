# pack-display-bedrock
This pack display is permanently integrated in the pack and can only be deleted by removing the file.

[![ingame](https://cdn.discordapp.com/attachments/586639642552565790/826751863754981376/Minecraft_31.03.2021_11_31_12.png)](https://github.com/YockerFX/pack-display-bedrock)

## How to use it:
you have to open your file explorer then go to the place where the packs are stored open the pack of your choice create a ui folder and copy the "debug_screen.json" files into the ui folder then you can edit the things like the "texture", "text" & "font_scale".

*Note: copy the pack_icon.png and paste it in the folder of the pack_icon.png after that you have to rename the copy to pack.png* 

```
resource_packs\your_pack\ui
```

## Code:
```javascript
//-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
// YockerFX
// https://github.com/YockerFX/pack-display-bedrock
//------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
{
  "namespace": "debug_screen",
  "access_button@common_buttons.light_content_button": {
    "$pressed_button_name": "button.access",
    "size": [
      20,
      20
    ],
    "offset": [
      20,
      20
    ],
    "anchor_to": "top_left",
    "anchor_from": "top_left",
    "bindings": [
      {
        "binding_name": "#access_screen_visible",
        "binding_name_override": "#visible"
      }
    ]
  },
  "watermark": {
    "type": "label",
    "text": "Pack Name§r\nMCBE: §b@YockerFX", // "\n" = line break
    "font_scale_factor": 1.2, // size of the fon
    "color": [
      1.0,
      1.0,
      1.0
    ], // color
    "shadow": true,
    "font_size": "small",
    "anchor_from": "top_right",
    "anchor_to": "top_right",
    "alpha": 10
  },
  "watermark_image": {
    "type": "image",
    "texture": "pack_icon.png", // displayed image
    "layer": 3,
    "offset": [
      -60,
      -2.5
    ], 
    "anchor_from": "top_right",
    "anchor_to": "top_right",
    "size": [
      16,
      16
    ]
  },
  "special_render": {
    "type": "custom",
    "renderer": "debug_screen_renderer"
  },
  "content_panel": {
    "type": "panel",
    "clips_children": false,
    "size": [
      "100%",
      "100%"
    ],
    "controls": [
      {
        "access_button@debug_screen.access_button": {}
      },
      {
        "special_render@debug_screen.special_render": {}
      },
      {
        "watermark@debug_screen.watermark": {}
      },
      {
        "watermark_image@debug_screen.watermark_image": {}
      }
    ]
  },
  "debug_screen@common.base_screen": {
    "send_telemetry": false,
    "screen_not_flushable": true,
    "render_game_behind": true,
    "is_showing_menu": false,
    "low_frequency_rendering": true,
    "is_modal": true,
    "should_steal_mouse": false,
    "render_only_when_topmost": false,
    "screen_draws_last": true,
    "always_accepts_input": true,
    "$screen_content": "debug_screen.content_panel",
    "$screen_animations": [],
    "$use_loading_bars": false
  }
}
```
