BUFF说明

BUFFID必须配置10000以上

重读BUFF（线上版本：只允许新增重读，不要删除或修改对应参数后重读，如有修改或删除BUFF请务必做好检测删除再重新给予）
buff系统需要把表头内的所有字段复制到自身的版本中，否则会引擎报错导致无法启动引擎

该功能请各位注意查看所有对应的后续扩展的配置字段，有效减少一些属性计算和常规的定时器触发。

不支持减属性，属性造成负数时会造成数据溢出！(0323引擎以后支持负数)
目前BUFF不支持配置负属性，加属性也不可以超过42Y限制（正负值溢出会出问题）
10000ID之前的系统类BUFF说明：
①BUFF图标显示：删除对应BUFFID图标字段配置编号即可
②第8列原有系统功能(如：麻痹、锁定、冰冻等)按需配置二进制行为
例：锁定需要(1.禁止走，2.禁止跑，4.禁止攻击，8. 禁止施法，16.禁止使用物品 64.禁止飞)
设置为1+2+4+8+16表格内填写31即可，原有-1配置需要重新配置，不可填写为-1
触发

QF触发字段：需配置BUFF表第20列(不配置则不会触发)根据对应需求填写所需的触发,若无功能需求则不填,减少引擎消耗

buff操作触发

buffchange

参数	类型	空	默认	注释
actor	object	否		玩家、怪物对象
buffid	integer	否		buffID
groupid	integer	否		组id
model	integer	否		操作类型
1=新增;
2=更新;
4=删除;
function buffchange(actor, buffid, groupid, model)
    release_print("打印常量",getconst(actor,"<$LOGINSTEP>"))
end

buff触发血量改变时

bufftriggerhpchange

特殊：该触发中不允许直接删除buff，包括buff组关系等影响的删除(会内存泄漏)
特殊：如果一定要删除请使用延时回调

参数	类型	空	默认	注释
actor	object	否		玩家
buff触发者为怪物时,
该参数无效
buffid	integer	否		buffid
buffGroup	integer	否		buff组
HP	integer	否		hp
buffHost	object	否		释放者对象
mon	object	否		怪物对象
buff触发者为玩家时,
该参数无效
result	integer	否		本次扣血
    function bufftriggerhpchange(actor,buffID,buffGroup,hp,buffHost,mon)
        return hp
    end

接口
添加buff

addbuff

参数	类型	空	默认	注释
base	object	否		玩家、怪物对象
buffid	integer	否		buff id，10000以后
time	integer	是		时间,对应buff表里维护的单位
OverLap	integer	是		叠加层数，默认1
objOwner	object	是		施放者
Abil	table	是		属性表 {[1]=200, [4]=20}，属性id=值
result	bool	否		是否添加成功
删除buff

delbuff

参数	类型	空	默认	注释
base	object	否		玩家、怪物对象
buffid	integer	否		buff id
获取buff信息

getbuffinfo

参数	类型	空	默认	注释
base	object	否		玩家、怪物对象
buffid	integer	否		buffid
type	integer	否	0	1=叠加层数
2=剩余时间
3=获取施法者对象
(对象离线返回nil)
4=获取额外属性
result	integer	否		返回值
获取buff模板信息

getstdbuffinfo

参数	类型	空	默认	注释
buffID	integer	否		buffID
id	integer	否		0:idx
1:名称;
2.组别;
3.配置时间;
4.配置属性;
result	integer	是	0	对应数值，不存在为0
获取角色所有buff

getallbuffid

参数	类型	空	默认	注释
player	object	否		玩家对象
result	table	是		buff列表
    local list_buff = getallbuffid(actor)
    for i, buffid in ipairs(list_buff) do
        release_print("buff",i,buffid)
    end

是否有buff

hasbuff

参数	类型	空	默认	注释
base	object	否		玩家、怪物对象
buffid	integer	否		buff id
result	bool	否		是否有该buff