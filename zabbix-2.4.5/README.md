
Zatree for zabbix 2.4.5 ��װ
==================================

1�������ļ�

git clone https://github.com/spide4k/zatree.git zatree

2��Ϊ�˼��ٱ༭�ļ���������������Ժ�zatreeֻ�ṩ��zabbix���Ϻõİ�

php��Ҫ֧��php-xml��php-gd��php-mysql

�ȱ��ݵ�ǰzabbix webĿ¼��Ų�ߣ�Ȼ���ѹzatree-zabbix-2.4.5.tar.gz��Ȼ���޸����������ļ�

3��zabbix���ݿ�
����ԴĿ¼��conf/zabbix.conf.php����Ŀ¼����

���ԭ�����������Ҳ˳�ֿ�������

4��֧��web interface,�޸������ļ� 
zatree/zabbix_config.php

'user'=>'xxx', //web��½���û���

'password'=>'xxx', //web��½������

'http_user'=>'xxx', //httpsweb��½���û���

'http_password'=>'xxx', //httpsweb��½������


���ƿ���zatree��zabbix
==================================

�뷢email��zhedou#163.com


����
==================================

QQ����Ⱥ��271659981

΢�Ŷ��ĺ�:yunweibang

��ά��,һ�����������ĺ�,ɨ����,����������

![image](https://raw.github.com/spide4k/zatree/master/zabbix-2.0.x/screenshots/yunweibang-weixin.jpg)


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

4:�����´���

Warning: array_key_exists() expects parameter 2 to be array, null given in zatree/ZabbixApiAbstract.class.php on line 255

Notice: Trying to get property of non-object in zatree/ZabbixApiAbstract.class.php on line 262

Warning: Invalid argument supplied for foreach() in zatree/graph.php online 130

�ڴ�������޸�php.ini������СΪXXX
memory_limit = XXXM

5:�Ƿ�֧����������ؼ��֣�

֧�֣��ؼ����ö��ŷָ�

6:����ѡ��Ĳ�ֵ��ʲô��˼��

��һ��ʱ������ֵ��ȥ��Сֵ�õ�һ�������Ȼ�����������������ѡ���һ��ʱ���ڵ�ͻ�������鿴�ǳ�����

7: ����������������ip��������������ʾ����������� �༭zabbix_ajax.php 

   43�д���ע��44�򿪣���֧��ip����43�д����44��ע�ͣ�֧��ip����
          43  $new_list[ip2long($each_host->host)]=$each_host;
          44  //$new_list[] = $each_host;

8: ���zabbix��2.2.1�汾���п��ܻᱨ

Call to undefined method CMacrosResolverHelper::resolveItemNames() in zabbix/include/classes/api/CLineGraphDraw_Zabbix.php on line 107
�������������zabbix > 2.2.1


С����
==================================

��������zatree��������а���, ���Զ����߽���С����

![image](https://raw.github.com/spide4k/zatree/master/zabbix-2.0.x/screenshots/IMG_7649.JPG)![image](https://raw.github.com/spide4k/zatree/master/zabbix-2.0.x/screenshots/IMG_7650.JPG)

