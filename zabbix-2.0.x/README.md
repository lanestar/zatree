
Zatree for zabbix 2.0.x ��װ
==================================

1�������ļ�

git clone https://github.com/spide4k/zatree.git zatree

2����������ļ�

����zabbix webĿ¼λ����/var/www/zabbix,����zabbixĿ¼

ZABBIX_PATH=/var/www/zabbix

��������ļ���Ŀ¼

cp -rf zatree/zabbix-2.0.x $ZABBIX_PATH/zatree

cd $ZABBIX_PATH/zatree/addfile

cp class.cchart_zabbix.php class.cgraphdraw_zabbix.php class.cimagetexttable_zabbix.php $ZABBIX_PATH/include/classes/

cp zabbix.php zabbix_chart.php $ZABBIX_PATH/

cp CItemValue.php $ZABBIX_PATH/api/classes/

3��֧��web interface,�޸������ļ�

vi $ZABBIX_PATH/zatree/zabbix_config.php

'user'=>'xxx', //web��½���û���

'passowrd'=>'xxx', //web��½������

4����������Zatree���,�޸�menu.inc.php��main.js

vi $ZABBIX_PATH/include/menu.inc.php

���285�е�294������

    285         'zatree'=>array(
    286                 'label' => _('Zatree'),
    287                 'user_type'                             => USER_TYPE_ZABBIX_USER,
    288                 'default_page_id'       => 0,
    289                 'force_disable_all_nodes' => true,
    290                 'pages' =>array(
    291                         array('url' => 'zabbix.php','label' => _('Zatree'),)
    292                         )
    293         
    294         ),      
    295         
    296         'login' => array(                               
    297                 'label'                                 => _('Login'),
    298                 'user_type'                             => 0,
    299                 'default_page_id'               => 0,

vi $ZABBIX_PATH/js/main.js

�滻106��

menus:                  {'empty': 0, 'view': 0, 'cm': 0, 'reports': 0, 'config': 0, 'admin': 0, 'zatree':0},

6�����ӷ�װ��api��


vi $ZABBIX_PATH/include/classes/api/API.php

��74�������75��'itemvalue'=>'CItemValue',

     74                 'usermedia' => 'CUserMedia',
     75                 'itemvalue'=>'CItemValue',
     76                 'webcheck' => 'CWebCheck'
     77         ); 

7����½zabbix���ڵ�������Կ���һ��Zatree�Ĳ˵���ʹ�÷�����ɵ�ϵ�


8: ����������������ip��������������ʾ����������� �༭zabbix_ajax.php 
   43�д���ע��44�򿪣���֧��ip����43�д����44��ע�ͣ�֧��ip����
          43  $new_list[ip2long($each_host->host)]=$each_host;
          44  //$new_list[] = $each_host;


����
==================================

QQ����Ⱥ��271659981, ΢�Ŷ��ĺ�:yunweibang

��������
==================================

1������Ŵ�

���Դ�php����ʾ���󣬿���ʲôԭ��

vi /etc/php.ini

display_errors = On

����web server,Ȼ����web��־

2��Fatal error: Call to undefined function json_encode() in /var/www/html/zabbix/zatree/ZabbixApiAbstract.class.php on line 220

��Ҫphp encode֧��

yum install php-pecl-json

�����������������У��Ҳ���php-pecl-json�����������������

yum install php-pear

pecl install json

echo "extension=json.so" > /etc/php.d/json.ini

3������Ҳ���ʾһ��2��ͼ��˵����ֱ��ʲ��������ϰ���㻻�������������޸�graph.php�ļ����е�widthֵ

    181 <img  src="<?php echo $small_graph; ?>" width="357" height="211" style="float:left;padding-top:4px;padding-left:4px;"  /> </a>

4���������Сͼ����ʾʱ��Σ��༭�ļ�include/classes/class.cchart_zabbix.php����2363��

     2363                 //      $this->drawDate();

5:�����´���

Warning: array_key_exists() expects parameter 2 to be array, null given in zatree/ZabbixApiAbstract.class.php on line 255

Notice: Trying to get property of non-object in zatree/ZabbixApiAbstract.class.php on line 262

Warning: Invalid argument supplied for foreach() in zatree/graph.php online 130

�ڴ�������޸�php.ini������СΪXXX
memory_limit = XXXM

6:�Ƿ�֧����������ؼ��֣�
֧�֣��ؼ����ö��ŷָ�

7:����ѡ��Ĳ�ֵ��ʲô��˼��
��һ��ʱ������ֵ��ȥ��Сֵ�õ�һ�������Ȼ�����������������ѡ���һ��ʱ���ڵ�ͻ�������鿴�ǳ�����

8: �������ֻ��ʾһ��ip�����⣬��Ϊ���ǵ�λ����������д����ip�����ǵ����������ַ��������Ծ���ʾ��������
���������
�༭zabbix_ajax.php��ע�����¼��У����ұ�֤��Ȧ�ı�����һ��
![image](https://raw.github.com/spide4k/zatree/master/zabbix-2.2.x/screenshots/3.jpg)


���ƿ���zatree��zabbix
==================================

�뷢email��zhedou#163.com


����
==================================

QQ����Ⱥ��271659981

΢�Ŷ��ĺ�:yunweibang

��ά��,һ�����������ĺ�,ɨ����,����������

![image](https://raw.github.com/spide4k/zatree/master/zabbix-2.0.x/screenshots/yunweibang-weixin.jpg)


С����
==================================


��������zatree��������а���, ���Զ����߽���С����


![image](https://raw.github.com/spide4k/zatree/master/zabbix-2.0.x/screenshots/IMG_7649.JPG)![image](https://raw.github.com/spide4k/zatree/master/zabbix-2.0.x/screenshots/IMG_7650.JPG)

