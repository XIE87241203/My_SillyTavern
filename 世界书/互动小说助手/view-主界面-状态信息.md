- 以下是故事中需要追踪的关键变量,以这些变量初始化当前状态: 
stat_data.场景状态: 
<%= JSON.stringify(getvar('stat_data.场景状态')) _%>

在场主要NPC资料: 
<%_ 
  var nps_list = getvar('stat_data.场景状态.在场的主要NPC');
  if (nps_list === undefined) nps_list = [];
  for (let i = 0; i < nps_list.length; i++) { 
    var item = getvar('stat_data.场景状态.在场的主要NPC')[i];
_%>
    NPC资料库.<%= item _%>: 
      <%= JSON.stringify(getvar('stat_data.NPC资料库.' + item)); _%>

<%_ } _%>