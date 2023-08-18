- 👋 Hi, I’m @RyanYu2004
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
RyanYu2004/RyanYu2004 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
Clock:
  AutoGetClock: false
  MainGuiId: home
  Name: '&b服务器指南'
  Lore:
  - '&a右键获得帮助'
  - '&e非消耗性道具'
  World:
  - world
  - world_nether
  - world_the_end
  - world_multi_paintings
GUI:
  'home':
    Name: '需要什么帮助？&k`'
    Item:
      '0  ':
        Position: 28
        ItemID: leather_chestplate
        Model: 
        Enchantment:
          ID: fortune
          Level: 1
        Name: 装扮管理
        Lore:
        - 点击管理你的装扮效果
        Message:
        - 
        Function:
          OpenAnotherGUI:
            Use: true
            Id: dress
          Command:
            Use: true
            CloseGui: false
            Content:
            - function economic_system:sound2
      '0 ':
        Position: 10
        ItemID: nether_star
        Model: 
        Enchantment:
          ID: fortune
          Level: 1
        Name: 设置标记点
        Lore:
        - 将您当前的位置设为标记点 &c与重生点无关！
        - 点数：16点/次（可透支消费）
        Message:
        - 
        Function:
          OpenAnotherGUI:
            Use: false
            Id: tp1
          Command:
            Use: true
            CloseGui: true
            Content:
            - spawn set
            - gamerule sendCommandFeedback false
            - schedule clear economic_system:feedback
            - scoreboard players remove @s Money 16
            - execute if entity @s[scores={Money=..15}] run title @s subtitle {"text":"消费功能已受限，请及时补充零钱数额！","color":"red"}
            - execute if entity @s[scores={Money=..15}] run title @s title {"text":"您正在透支消费！","color":"red"}
            - function economic_system:sound
            - schedule function economic_system:feedback 1s
      '0':
        Position: 11
        ItemID: ender_eye
        Model: 
        Enchantment:
          ID: fortune
          Level: 1
        Name: 传送至标记点
        Lore:
        - 点击传送至已设标记点
        - 点数：64点/次（可透支消费）
        Message:
        - 
        Function:
          OpenAnotherGUI:
            Use: false
            Id: tp1
          Command:
            Use: true
            Content:
            - spawn
            - gamerule sendCommandFeedback false
            - schedule clear economic_system:feedback
            - scoreboard players remove @s Money 64
            - execute if entity @s[scores={Money=..64}] run title @s subtitle {"text":"消费功能已受限，请及时补充零钱数额！","color":"red"}
            - execute if entity @s[scores={Money=..64}] run title @s title {"text":"您正在透支消费！","color":"red"}
            - function economic_system:sound
            - schedule function economic_system:feedback 1s
      '1':
        Position: 12
        ItemID: ender_pearl
        Model: 
        Enchantment:
          ID: fortune
          Level: 1
        Name: 传送至服务器固定地点
        Lore:
        - 点击选择想要传送的固定地点
        - 点数：0~100m 免费
        - 100~200m 16点/次
        - 200~500m 32点/次
        - 500~1000m 64点/次
        - 1000~5000m 128点/次
        - 5000m及以上 256点/次
        - 跨维度 256点/次
        Message:
        - 
        Function:
          OpenAnotherGUI:
            Use: true
            Id: tp1
          Command:
            Use: true
            Content:
            - function economic_system:sound2
      '2':
        Position: 19
        ItemID: experience_bottle
        Enchantment:
          ID: fortune
          Level: 1
        Name: 获取、生成或消除道具
        Lore:
        - 点击获取、生成或消除道具
        Function:
          Command:
            Use: true
            CloseGui: false
            Content:
            - function economic_system:sound3
            RunAsOp: true
          OpenAnotherGUI:
            Use: true
            Id: get
      '3':
        Position: 20
        ItemID: light
        Enchantment:
          ID: fortune
          Level: 1
        Name: 说明书
        Lore:
        - 点击获得该指南使用提示
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - tellraw @s 1
            - function economic_system:sound4
            RunAsOp: true
          OpenAnotherGUI:
            Use: false
            Id: get
      '4':
        Position: 21
        ItemID: name_tag
        Enchantment:
          ID: fortune
          Level: 1
        Name: 职业
        Lore:
        - 点击选择职业
        Function:
          Command:
            Use: true
            CloseGui: false
            Content:
            - function economic_system:sound6
            RunAsOp: true
          OpenAnotherGUI:
            Use: true
            Id: job
      '5':
        Position: 29
        ItemID: gold_nugget
        Model: 10001
        Enchantment:
          ID: fortune
          Level: 1
        Name: 零钱管理
        Lore:
        - 点击选择要办理的业务
        Function:
          Command:
            Use: true
            CloseGui: false
            Content:
            - function economic_system:sound2
            RunAsOp: true
          OpenAnotherGUI:
            Use: true
            Id: money
      '5 ':
        Position: 30
        ItemID: map
        Enchantment:
          ID: fortune
          Level: 1
        HideEnchant: true
        HideAttribute: true
        Name: 数字输入器
        Lore:
        - 点击输入数字
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - ap use give
            - function economic_system:sound2
            RunAsOp: true
      '5  ':
        Position: 15
        ItemID: elytra
        Enchantment:
          ID: fortune
          Level: 1
        HideEnchant: true
        HideAttribute: true
        Name: 飞行模式
        Lore:
        - 点击打开/关闭飞行模式
        Function:
          Command:
            Use: true
            CloseGui: false
            Content:
            - fly
            - function economic_system:sound2
            RunAsOp: true
      '5   ':
        Position: 16
        ItemID: book
        Enchantment:
          ID: fortune
          Level: 1
        HideEnchant: true
        HideAttribute: true
        Name: 测试
        Lore:
        - 点击测试
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - give <-s ad>
            - function economic_system:sound2
            RunAsOp: true
      '6':
        Position: 24
        ItemID: end_crystal
        Enchantment:
          ID: fortune
          Level: 1
        Name: 服务器管理
        Lore:
        - 点击选择要执行的命令
        Function:
          Command:
            Use: true
            CloseGui: false
            Content:
            - function economic_system:sound8
            RunAsOp: true
          OpenAnotherGUI:
            Use: true
            Id: admin
      '7':
        Position: 25
        ItemID: repeating_command_block
        Enchantment:
          ID: fortune
          Level: 1
        Name: 其他命令
        Lore:
        - 点击选择要执行的命令
        Function:
          Command:
            Use: true
            CloseGui: false
            Content:
            - function economic_system:sound2
            RunAsOp: true
          OpenAnotherGUI:
            Use: true
            Id: other_commands
      '8':
        Position: 34
        ItemID: structure_void
        Enchantment:
          ID: fortune
          Level: 1
        Name: 关闭菜单
        Lore:
        - 
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - function economic_system:sound9
            RunAsOp: true
          OpenAnotherGUI:
            Use: false
            Id: other_commands
      '9':
        Position: 0
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '9 ':
        Position: 2
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '9  ':
        Position: 3
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '9   ':
        Position: 4
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '9    ':
        Position: 5
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '9     ':
        Position: 8
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '9      ':
        Position: 9
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '10':
        Position: 18
        ItemID: black_stained_glass_pane
        Name: 下界主题装饰
      '11':
        Position: 27
        ItemID: gray_stained_glass_pane
        Name: 下界主题装饰
      '11 ':
        Position: 36
        ItemID: gray_stained_glass_pane
        Name: 下界主题装饰
      '11  ':
        Position: 38
        ItemID: gray_stained_glass_pane
        Name: 下界主题装饰
      '12':
        Position: 13
        ItemID: orange_stained_glass_pane
        Name: 下界主题装饰
      '12 ':
        Position: 22
        ItemID: orange_stained_glass_pane
        Name: 下界主题装饰
      '12  ':
        Position: 31
        ItemID: orange_stained_glass_pane
        Name: 下界主题装饰
      '12   ':
        Position: 40
        ItemID: orange_stained_glass_pane
        Name: 下界主题装饰
      '12    ':
        Position: 39
        ItemID: orange_stained_glass_pane
        Name: 下界主题装饰
      '13':
        Position: 1
        ItemID: yellow_stained_glass_pane
        Name: 下界主题装饰
      '14':
        Position: 6
        ItemID: white_stained_glass_pane
        Name: 下界主题装饰
      '14 ':
        Position: 7
        ItemID: white_stained_glass_pane
        Name: 下界主题装饰
      '15':
        Position: 37
        ItemID: orange_stained_glass_pane
        Name: 下界主题装饰
      '16':
        Position: 14
        ItemID: weeping_vines
        Name: 下界主题装饰
      '16 ':
        Position: 23
        ItemID: weeping_vines
        Name: 下界主题装饰
      '16  ':
        Position: 32
        ItemID: weeping_vines
        Name: 下界主题装饰
      '17':
        Position: 41
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '17 ':
        Position: 42
        ItemID: red_stained_glass_pane
        Name: 下界主题装饰
      '18':
        Position: 35
        ItemID: cyan_stained_glass_pane
        Name: 下界主题装饰
      '18 ':
        Position: 43
        ItemID: cyan_stained_glass_pane
        Name: 下界主题装饰
      '19':
        Position: 44
        ItemID: brown_stained_glass_pane
        Name: 下界主题装饰
      '20':
        Position: 17
        ItemID: twisting_vines
        Name: 下界主题装饰
      '20 ':
        Position: 26
        ItemID: twisting_vines
        Name: 下界主题装饰

  'tp1':
    Name: 主世界
    Item:
      '0':
        Position: 52
        ItemID: compass
        Enchantment:
          ID: fortune
          Level: 1
        Name: 返回上一级（主菜单）
        Lore:
        - 
        Function:
          Command:
            Use: true
            Content:
            - function economic_system:sound9
          OpenAnotherGUI:
            Use: true
            Id: home
      '0 ':
        Position: 53
        ItemID: structure_void
        Enchantment:
          ID: fortune
          Level: 1
        Name: 关闭菜单
        Lore:
        - 
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - function economic_system:sound9
          OpenAnotherGUI:
            Use: false
            Id: home
      '1':
        Position: 0
        ItemID: dark_oak_wood
        Enchantment:
          ID: fortune
          Level: 1
        Name: Minecraft Mansion
        Lore:
        - 服务器行政楼
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=minecraft_mansion_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=minecraft_mansion_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=minecraft_mansion_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=minecraft_mansion_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=minecraft_mansion_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=minecraft_mansion_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=minecraft_mansion_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '2':
        Position: 1
        ItemID: furnace
        Name: ISEC (Items Storage and Exchange Centre)
        Enchantment:
          ID: fortune
          Level: 1
        Lore:
        - 物品存储与交换中心
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=isec_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=isec_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=isec_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=isec_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=isec_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=isec_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=isec_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '3':
        Position: 2
        ItemID: gold_block
        Enchantment:
          ID: fortune
          Level: 1
        Name: Lake Bank
        Lore:
        - 湖·银行
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=lake_bank_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=lake_bank_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=lake_bank_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=lake_bank_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=lake_bank_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=lake_bank_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=lake_bank_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '4':
        Position: 3
        ItemID: green_dye
        Enchantment:
          ID: fortune
          Level: 1
        Name: Plant-processing-and-dye-technology Base
        Lore:
        - 植物加工与染料工艺基地
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=ppdtb_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=ppdtb_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=ppdtb_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=ppdtb_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=ppdtb_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=ppdtb_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=ppdtb_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '5':
        Position: 4
        ItemID: beacon
        Enchantment:
          ID: fortune
          Level: 1
        Name: Shopping Mall
        Lore:
        - 商业广场
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=shopping_mall_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=shopping_mall_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=shopping_mall_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=shopping_mall_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=shopping_mall_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=shopping_mall_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=shopping_mall_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '6':
        Position: 5
        ItemID: white_stained_glass
        Enchantment:
          ID: fortune
          Level: 1
        Name: Pixel Centre
        Lore:
        - Pixel商业中心
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=pixel_centre_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=pixel_centre_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=pixel_centre_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=pixel_centre_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=pixel_centre_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=pixel_centre_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=pixel_centre_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '7':
        Position: 6
        ItemID: cyan_stained_glass
        Enchantment:
          ID: fortune
          Level: 1
        Name: Technology Mansion
        Lore:
        - 科技大厦
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=technology_mansion_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=technology_mansion_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=technology_mansion_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=technology_mansion_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=technology_mansion_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=technology_mansion_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=technology_mansion_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '8':
        Position: 7
        ItemID: bricks
        Enchantment:
          ID: fortune
          Level: 1
        Name: Minecraft University
        Lore:
        - MC大学
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=minecraft_university_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=minecraft_university_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=minecraft_university_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=minecraft_university_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=minecraft_university_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=minecraft_university_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=minecraft_university_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '9':
        Position: 9
        ItemID: farmland
        Enchantment:
          ID: fortune
          Level: 1
        Name: Farmland
        Lore:
        - 农业区
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=farmland_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=farmland_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=farmland_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=farmland_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=farmland_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=farmland_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=farmland_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '10':
        Position: 10
        ItemID: tnt
        Enchantment:
          ID: fortune
          Level: 1
        Name: Trial Area
        Lore:
        - 试验田 &C注意危险！
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=trial_area_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=trial_area_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=trial_area_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=trial_area_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=trial_area_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=trial_area_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=trial_area_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '11':
        Position: 18
        ItemID: jack_o_lantern
        Enchantment:
          ID: fortune
          Level: 1
        Name: Hall&k~&rween Isl&k~&rnd&k~
        Lore:
        - 万&k~&r圣节岛&k~
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=halloween_island_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=halloween_island_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=halloween_island_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=halloween_island_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=halloween_island_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=halloween_island_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=halloween_island_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '12':
        Position: 27
        ItemID: elytra
        Enchantment:
          ID: fortune
          Level: 1
        Name: Sky City
        Lore:
        - 天空之城
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=sky_city_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=sky_city_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=sky_city_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=sky_city_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=sky_city_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=sky_city_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=sky_city_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2
      '13':
        Position: 28
        ItemID: dark_oak_sapling
        Enchantment:
          ID: fortune
          Level: 1
        Name: Cottage In Wild
        Lore:
        - 远郊别墅
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - gamerule sendCommandFeedback false
            - execute if entity @s[tag=!to_tp] run tag @s add to_tp
            - execute if dimension overworld if entity @e[tag=cottage_in_wild_tpset,distance=..100] if entity @s[tag=to_tp,scores={Money=0..}] run tag @s add tp_free
            - execute if dimension overworld if entity @e[tag=cottage_in_wild_tpset,distance=100..200] if entity @s[tag=to_tp,scores={Money=16..}] run tag @s add tp_16
            - execute if dimension overworld if entity @e[tag=cottage_in_wild_tpset,distance=200..500] if entity @s[tag=to_tp,scores={Money=32..}] run tag @s add tp_32
            - execute if dimension overworld if entity @e[tag=cottage_in_wild_tpset,distance=500..1000] if entity @s[tag=to_tp,scores={Money=64..}] run tag @s add tp_64
            - execute if dimension overworld if entity @e[tag=cottage_in_wild_tpset,distance=1000..5000] if entity @s[tag=to_tp,scores={Money=128..}] run tag @s add tp_128
            - execute if dimension overworld if entity @e[tag=cottage_in_wild_tpset,distance=5000..] if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute unless dimension overworld if entity @s[tag=to_tp,scores={Money=256..}] run tag @s add tp_256
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"余额不足！","color":"red"}
            - execute if entity @s[tag=to_tp,tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Insufficient balance!","color":"red"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run execute as @e[tag=cottage_in_wild_tpset] at @s run tp @p[tag=to_tp] @s
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s title {"text":"成功！","color":"aqua"}
            - execute if entity @s[tag=to_tp] unless entity @s[tag=!tp_free,tag=!tp_16,tag=!tp_32,tag=!tp_64,tag=!tp_128,tag=!tp_256] run title @s subtitle {"text":"Done!","color":"aqua"}
            - execute if entity @s[tag=tp_16] run scoreboard players remove @s Money 16
            - execute if entity @s[tag=tp_32] run scoreboard players remove @s Money 32
            - execute if entity @s[tag=tp_64] run scoreboard players remove @s Money 64
            - execute if entity @s[tag=tp_128] run scoreboard players remove @s Money 128
            - execute if entity @s[tag=tp_256] run scoreboard players remove @s Money 256
            - execute if entity @s[tag=to_tp] run tag @s remove to_tp
            - execute if entity @s[tag=tp_16] run tag @s remove tp_16
            - execute if entity @s[tag=tp_32] run tag @s remove tp_32
            - execute if entity @s[tag=tp_64] run tag @s remove tp_64
            - execute if entity @s[tag=tp_128] run tag @s remove tp_128
            - execute if entity @s[tag=tp_256] run tag @s remove tp_256
            - execute if entity @s[tag=tp_free] run tag @s remove tp_free
            - function economic_system:sound2

  'job':
    Name: 选择职业
    Item:
      '1':
        Position: 11
        ItemID: barrier
        Enchantment:
          ID: fortune
          Level: 1
        Name: 关闭职业
        Lore:
        - None
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - gamerule sendCommandFeedback false
            - team join None
            - title @s title {"text":"您已关闭职业","color":"red"}
            - title @s subtitle {"text":"You have no jobs now","color":"red"}
            - function economic_system:sound5
      '2':
        Position: 19
        ItemID: golden_sword
        Enchantment:
          ID: fortune
          Level: 1
        Name: 猎人
        Lore:
        - Hunter
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - gamerule sendCommandFeedback false
            - team join Hunter
            - title @s title {"text":"你现在是猎人","color":"gold"}
            - title @s subtitle {"text":"You are a Hunter now","color":"gold"}
            - function economic_system:sound5
      '3':
        Position: 20
        ItemID: golden_pickaxe
        Enchantment:
          ID: fortune
          Level: 1
        Name: 矿工
        Lore:
        - Miner
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - gamerule sendCommandFeedback false
            - team join Miner
            - title @s title {"text":"你现在是矿工","color":"green"}
            - title @s subtitle {"text":"You are a Miner now","color":"green"}
            - function economic_system:sound5
      '4':
        Position: 21
        ItemID: golden_hoe
        Enchantment:
          ID: fortune
          Level: 1
        Name: 农民
        Lore:
        - Farmer
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - gamerule sendCommandFeedback false
            - team join Farmer
            - title @s title {"text":"你现在是农民","color":"light_purple"}
            - title @s subtitle {"text":"You are a Farmer now","color":"light_purple"}
            - function economic_system:sound5
      '5':
        Position: 28
        ItemID: grass_block
        Enchantment:
          ID: fortune
          Level: 1
        Name: 肝帝
        Lore:
        - Builder
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - gamerule sendCommandFeedback false
            - team join Builder
            - title @s title {"text":"你现在是建造师","color":"light_purple"}
            - title @s subtitle {"text":"You are a Builder now","color":"light_purple"}
            - function economic_system:sound5
      '6':
        Position: 29
        ItemID: fishing_rod
        Enchantment:
          ID: fortune
          Level: 1
        Name: 渔夫
        Lore:
        - Fisherman
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - gamerule sendCommandFeedback false
            - team join Fisherman
            - title @s title {"text":"你现在是渔夫","color":"dark_aqua"}
            - title @s subtitle {"text":"You are a Fisherman now","color":"dark_aqua"}
            - function economic_system:sound5
      '7':
        Position: 30
        ItemID: brewing_stand
        Enchantment:
          ID: fortune
          Level: 1
        Name: 药剂师
        Lore:
        - Chemist
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - gamerule sendCommandFeedback false
            - team join Chemist
            - title @s title {"text":"你现在是药剂师","color":"dark_purple"}
            - title @s subtitle {"text":"You are a Chemist now","color":"dark_purple"}
            - function economic_system:sound5
      '8':
        Position: 15
        ItemID: chain_command_block
        Enchantment:
          ID: fortune
          Level: 1
        Name: 管理员
        Lore:
        - Administrator
        Function:
          Command:
            CloseGui: true
            Use: true
            Content:
            - gamerule sendCommandFeedback false
            - - execute if entity @s[scores={Played_time=14400000..}] run team join Admin
            - - execute unless entity @s[scores={Played_time=14400000..}] run tellraw @s {"text":"您现在游戏累计时长未到200小时，不能选择该职业","color":"red"}
            - - execute unless entity @s[scores={Played_time=14400000..}] run playsound minecraft:block.note_block.didgeridoo ambient @s ~ ~ ~ 1 1 1
            - - execute if entity @s[scores={Played_time=14400000..}] run title @s title {"text":"你现在是管理员","color":"yellow"}
            - - execute if entity @s[scores={Played_time=14400000..}] run title @s subtitle {"text":"You are an Administrator now","color":"yellow"}
            - - execute if entity @s[scores={Played_time=14400000..}] run function economic_system:sound7
      '9':
        Position: 43
        ItemID: compass
        Enchantment:
          ID: fortune
          Level: 1
        Name: 返回上一级
        Lore:
        - 
        Function:
          Command:
            Use: false
            Content:
            - say 钟表菜单
          OpenAnotherGUI:
            Use: true
            Id: home
      '10':
        Position: 44
        ItemID: structure_void
        Enchantment:
          ID: fortune
          Level: 1
        Name: 关闭菜单
        Lore:
        - 
        Function:
          Command:
            Use: true
            CloseGui: true
            Content:
            - 
          OpenAnotherGUI:
            Use: false
            Id: home
      '11':
        Position: 0
        ItemID: light_blue_stained_glass_pane
        Name: 平原主题装饰
      '11 ':
        Position: 3
        ItemID: light_blue_stained_glass_pane
        Name: 平原主题装饰
      '11  ':
        Position: 4
        ItemID: light_blue_stained_glass_pane
        Name: 平原主题装饰
      '11   ':
        Position: 5
        ItemID: light_blue_stained_glass_pane
        Name: 平原主题装饰
      '11    ':
        Position: 6
        ItemID: light_blue_stained_glass_pane
        Name: 平原主题装饰
      '11     ':
        Position: 8
        ItemID: light_blue_stained_glass_pane
        Name: 平原主题装饰
      '12':
        Position: 1
        ItemID: white_stained_glass_pane
        Name: 平原主题装饰
      '12 ':
        Position: 2
        ItemID: white_stained_glass_pane
        Name: 平原主题装饰
      '12  ':
        Position: 7
        ItemID: white_stained_glass_pane
        Name: 平原主题装饰
      '13':
        Position: 14
        ItemID: lime_stained_glass_pane
        Name: 平原主题装饰
      '13 ':
        Position: 22
        ItemID: lime_stained_glass_pane
        Name: 平原主题装饰
      '13  ':
        Position: 23
        ItemID: lime_stained_glass_pane
        Name: 平原主题装饰
      '13   ':
        Position: 24
        ItemID: lime_stained_glass_pane
        Name: 平原主题装饰
      '14':
        Position: 31
        ItemID: yellow_stained_glass_pane
        Name: 平原主题装饰
      '15':
        Position: 32
        ItemID: brown_stained_glass_pane
        Name: 平原主题装饰
      '15 ':
        Position: 41
        ItemID: brown_stained_glass_pane
        Name: 平原主题装饰
      '15  ':
        Position: 50
        ItemID: brown_stained_glass_pane
        Name: 平原主题装饰
      '16':
        Position: 46
        ItemID: grass
        Name: 平原主题装饰
      '16 ':
        Position: 48
        ItemID: grass
        Name: 平原主题装饰
      '16  ':
        Position: 51
        ItemID: grass
        Name: 平原主题装饰
      '16   ':
        Position: 53
        ItemID: grass
        Name: 平原主题装饰
      '17':
        Position: 45
        ItemID: rose_bush
        Name: 平原主题装饰
      '18':
        Position: 47
        ItemID: peony
        Name: 平原主题装饰
      '19':
        Position: 49
        ItemID: campfire
        Name: 平原主题装饰
      '20':
        Position: 40
        ItemID: frogspawn
        Name: 平原主题装饰
      '21':
        Position: 52
        ItemID: lilac
        Name: 平原主题装饰
      '22':
        Position: 17
        ItemID: sunflower
        Name: 平原主题装饰

  'get':
    Name: 获取或生成道具
    Item:
      '1':
        Position: 0
        ItemID: structure_block
        Name: 生成结构方块
        Lore:
        - 第一行
        Function:
          Command:
            Use: false
            Content:
            - resadmin tp mcm
          OpenAnotherGUI:
            Use: true
            Id: structure
      '2':
        Position: 53
        ItemID: compass
        Enchantment:
          ID: fortune
          Level: 1
        Name: 返回上一级
        Lore:
        - 第六行
        Function:
          Command:
            Use: false
            Content:
            - say 钟表菜单
          OpenAnotherGUI:
            Use: true
            Id: home

  'structure':
    Name: 选择并在腿部生成结构方块
    Item:
      '1':
        Position: 0
        ItemID: black_stained_glass_pane
        Name: 基础设施
        Enchantment:
          ID: fortune
          Level: 1
        HideEnchant: true
        HideAttribute: true
        Lore:
        - 第一行
        Function:
          Command:
            Use: false
            Content:
            - resadmin tp mcm
          OpenAnotherGUI:
            Use: false
            Id: structure
      '4':
        Position: 53
        ItemID: compass
        Enchantment:
          ID: fortune
          Level: 1
        Name: 返回上一级
        Lore:
        - 第六行
        Function:
          Command:
            Use: false
            Content:
            - say 钟表菜单
          OpenAnotherGUI:
            Use: true
            Id: get
      '5':
        Position: 52
        ItemID: barrier
        Enchantment:
          ID: fortune
          Level: 1
        Name: 清除结构方块
        Lore:
        - 第六行
        Function:
          Command:
            Use: true
            Content:
            - fill ~-2 ~-2 ~-2 ~2 ~2 ~2 minecraft:air replace minecraft:structure_block
          OpenAnotherGUI:
            Use: false
            Id: get
      '3':
        Position: 1
        ItemID: chain
        Name: 朴实的分割线
        Lore:
        - 第一行
        Function:
          Command:
            Use: false
            Content:
            - resadmin tp mcm
          OpenAnotherGUI:
            Use: false
            Id: structure
      '2':
        Position: 2
        ItemID: red_terracotta
        Name: 大道1
        Lore:
        - 第一行
        Function:
          Command:
            Use: true
            Content:
            - setblock ~ ~ ~ minecraft:structure_block[mode=load]{metadata:"",mirror:"NONE",ignoreEntities:1b,powered:0b,seed:0L,author:"Fish_moon_",rotation:"NONE",posX:-19,mode:"LOAD",posY:-1,sizeX:47,posZ:1,integrity:1.0f,showair:0b,name:"minecraft:avenue1",sizeY:48,sizeZ:36,showboundingbox:1b}
          OpenAnotherGUI:
            Use: false
            Id: structure
