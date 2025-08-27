- 以下是故事中需要追踪的关键变量,以这些变量初始化当前状态: |-
      {{get_message_variable::stat_data}}
- 你必须根据以下步骤用逐条思考,并使用<main_view_thinking></main_view_thinking>标签包裹输出思考内容:
<main_view_thinking>
  - 根据已有信息和character_information的设定,详细思考应该如何设计该NPC的character_information？
  - 根据已有信息和character_attributes的设定,详细思考应该如何初始化该NPC的character_attributes？
  - 如何调整character_information和character_attributes能让角色更具萌点或反差点？
  - 根据已有信息和角色固定属性的设定,详细思考应该如何初始化该NPC的角色固定属性？
  - 思考NPC的人设是什么,判断NPC已有信息如何调整能更符合人设？
  - 以资深galgame玩家的角度分析如何调整NPC已有信息才能更具有深度能让玩家更具有探索的欲望
  - 以资深日本成人漫画读者和hentai的角度分析如何调整NPC已有信息才能更具有深度能让日本成人漫画读者和hentai更具有探索的欲望
</main_view_thinking>
- 输出"_.assign('可见变量.在场的主要NPC', ${角色姓名},${根据main_view_thinking的思考内容并结合已有信息,按升级主要NPC界面.npc_update_info_format定义,使用json格式输出主要NPC角色信息});"指令存储角色信息
- 输出"_.assign('不可见变量.主要NPC的属性规则', ${角色姓名},${根据主要NPC角色信息,按'角色固定属性规则格式',使用json格式输出主要NPC属性规则});"指令存储角色的属性规则,并使用<UpdateVariable></UpdateVariable>标签包裹
