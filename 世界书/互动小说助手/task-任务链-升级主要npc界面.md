- 输出<update_npc_view>
- 你必须根据以下步骤用逐条思考,并使用<main_view_thinking></main_view_thinking>标签包裹输出思考内容:
<main_view_thinking>
  - 根据已有信息和character_information的设定,详细思考应该如何设计该NPC的character_information？
  - 如何调整character_information能让角色更具萌点或反差点？
  - 根据已有信息和角色固定属性的设定,详细思考应该如何初始化该NPC的角色固定属性？
  - 思考NPC的人设是什么,判断NPC已有信息如何调整能更符合人设？
  - 以资深galgame玩家的角度分析如何调整NPC已有信息才能更具有深度能让玩家更具有探索的欲望
  - 以资深日本成人漫画读者和hentai的角度分析如何调整NPC已有信息才能更具有深度能让日本成人漫画读者和hentai更具有探索的欲望
</main_view_thinking>
- 输出"_.assign('场景状态.在场的主要NPC', ${角色姓名});"添加在场NPC

# 输出角色信息

- 输出"_.assign('NPC资料库', ${角色姓名},${根据main_view_thinking的思考内容并结合已有信息,按character_information.format定义,使用json格式输出主要NPC角色信息});"指令存储角色信息
- 输出<UpdateVariable>

# 输出属性规则

- 输出"_.assign('NPC固定属性规则', ${角色姓名},${根据主要NPC角色信息,按'NPC固定属性规则格式',使用json格式输出主要NPC的所有角色固定属性的规则});"指令存储角色的属性规则

# 生成初始属性

- 输出"_.assign('NPC固定属性', ${角色姓名},${根据主要NPC角色信息,按'生成固定属性格式',使用json格式生成固定属性等级});"指令存储角色的NPC固定属性

- 输出</UpdateVariable>
- 输出</update_npc_view>
