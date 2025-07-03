创建临时NPC

createnpc

参数	类型	空	默认	注释
map	string	否		地图编号
X	integer	否		X坐标
Y	integer	否		Y坐标
NPC	string	否		NPC信息
json字符串
[[
    注意：自定义NPC的Idx不允许与配置表中的NPCID重复。
    Idx重复的NPC不会被创建出来。
]]
local npcInfo = {
    ["Idx"] =  npcidx,  -- 自定义NPC的Idx，NPC点击触发时，触发参数会传回Idx值
    ["npcname"] =  "测试", -- NPC名称
    ["appr"] =   7,  -- NPC外形效果
    ["script"] =   'NewNPC'  -- NPC相关脚本名称，表示Envir\Market_def\NewNPC.txt
}
createnpc(mapID,x,y,tbl2json(npcInfo))

删除NPC

delnpc

参数	类型	空	默认	注释
name	string	否		NPC名称
map	string	否		地图编号
根据ID获取NPC对象

getnpcbyindex

参数	类型	空	默认	注释
NPCIndex	int	否		NPC索引（NPC配置表中的ID）
npc	object	否		NPC对象
移动到指定NPC附近

opennpcshowex

参数	类型	空	默认	注释
play	object	否		玩家对象
NPCIndex	int	否		NPC索引（NPC配置表中的ID）
nRange	int	否		范围值，
不在此范围内则移动到NPC附近
nRange2	int	否		范围值2，移动到NPC附近的范围内
1. NPC不在当前地图时: nRange>0: 瞬移传送到NPC附近; nRange=0: 不传送;
2. NPC在当前地图时: nRange>0: 瞬移传送到NPC附近; nRange=0: 导航到NPC附近;

获取当前NPC对象

getcurrnpc

参数	类型	空	默认	注释
player	object	否		玩家对象
result	object	否		返回值，当前的NPC对象
设置NPC特效

setnpceffect

参数	类型	空	默认	注释
player	object	否		玩家对象
NPCIndex	int	否		NPC索引（NPC配置表中的ID）
Effect	int	否		特效ID
5055-感叹号
5056-问号
X	int	否		X坐标
Y	int	否		Y坐标
当X、Y<0时，默认取NPC的坐标

删除NPC特效

delnpceffect

参数	类型	空	默认	注释
player	object	否		玩家对象
NPCIndex	int	否		NPC索引（NPC配置表中的ID）
关闭当前的NPC对话框

close

参数	类型	空	默认	注释
player	object	否		玩家对象
获取NPC对象的Idx

getnpcindex

参数	类型	空	默认	注释
npc	object	否		NPC对象
result	int	否		NPC索引
（NPC配置表中的ID）