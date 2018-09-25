
������ 
========

__Ŀ¼__

-  [AbnormalData](#abnormaldata)  �쳣����
-  [Advert](#advert)  ����ƹ�
-  [App](#app)  Ӧ��
-  [Auth](#auth)  ��������֤��Ϣ
-  [BloodPressureData](#bloodpressuredata)  Ѫѹ����
-  [CELL](#cell)  ��վ��ʶ
-  [CasePage](#casepage)  �û�����
-  [Community](#community)  ����
-  [CommunityInviteMessage](#communityinvitemessage)  ����������Ϣ
-  [CommunityJoinMessage](#communityjoinmessage)  ������������
-  [CommunityLeaveMessage](#communityleavemessage)  �����뿪����
-  [CommunityMessage](#communitymessage)  ����ϵͳ��Ϣ
-  [CommunityNotification](#communitynotification)  ����֪ͨ
-  [Device](#device)  �豸��Ϣ
-  [DeviceToken](#devicetoken)  �ն˱�ʶ
-  [EmailConfirm](#emailconfirm)  Emailȷ��
-  [ExpertPage](#expertpage)  ר����Դ
-  [Group](#group)  ����
-  [GroupInviteCode](#groupinvitecode)  С��������Ϣ
-  [GroupNotification](#groupnotification)  ��ͥȦ֪ͨ
-  [HeartRateData](#heartratedata)  ��������
-  [HeartRateNotification](#heartratenotification)  �����쳣֪ͨ��Ϣ
-  [Imei](#imei)  IMEI����
-  [LocationCache](#locationcache)  ����λ�û���
-  [LocationData](#locationdata)  ��λ����
-  [LocationNotification](#locationnotification)  λ���쳣֪ͨ��Ϣ
-  [MediaData](#mediadata)  ͨ��upload�ϴ���ý������
-  [MediaMessage](#mediamessage)  ý����Ϣ
-  [MediaPage](#mediapage)  ý����Դ
-  [Member](#member)  С���Ա
-  [Message](#message)  ������Ϣ
-  [MsgNotification](#msgnotification)  Message֪ͨ��Ϣ
-  [Notification](#notification)  ����֪ͨ
-  [NotificationService](#notificationservice)  ���ͷ���
-  [Page](#page)  ��Դ����
-  [PageComment](#pagecomment)  ����
-  [PageStar](#pagestar)  ����
-  [PasswordResetNotify](#passwordresetnotify)  Email��������֪ͨ
-  [PasswordResetRequest](#passwordresetrequest)  Email��������ȷ��
-  [PedometerData](#pedometerdata)  �Ʋ�����
-  [Person](#person)  ��Ա��Ϣ
-  [PostureData](#posturedata)  ��������
-  [PowerData](#powerdata)  ��������
-  [PowerNotification](#powernotification)  �͵�֪ͨ
-  [RegisterRequest](#registerrequest)  Emailע��ȷ��
-  [RfidData](#rfiddata)  ��������
-  [SedentaryData](#sedentarydata)  ��������
-  [ServicePage](#servicepage)  �û�����
-  [SettingAlert](#settingalert)  �¼�����
-  [SettingFence](#settingfence)  Χ��
-  [SettingSosNumber](#settingsosnumber)  �������
-  [ShortMessage](#shortmessage)  ���ŷ�������
-  [ShortMessageChecksum](#shortmessagechecksum)  ������֤�뷢������
-  [ShortMessageSos](#shortmessagesos)  ���ȶ��ŷ�������
-  [SimPhone](#simphone)  SIM����
-  [SleepData](#sleepdata)  ˯������
-  [SleepDataSleep](#sleepdatasleep)  ����
-  [SosData](#sosdata)  ��������
-  [SosNotification](#sosnotification)  Sos֪ͨ��Ϣ
-  [SysMessage](#sysmessage)  ϵͳ��Ϣ
-  [TextMessage](#textmessage)  �ı���Ϣ
-  [TextPage](#textpage)  �ı���Դ
-  [UploadFile](#uploadfile)  �ļ�����
-  [WIFI](#wifi)  ��վ��ʶ
-  [WearData](#weardata)  �������
-  [WeatherCache](#weathercache)  ��������



# abnormaldata

�쳣����(��ʱ����)

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| abnormal_type | �쳣���� | Int |  |  | False | 0 |  |
| abnormal_code | �쳣��� | Int |  |  | False | 0 |  |


# advert

����ƹ�

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| text | ���� | String | 1 | 200 | True |  |  |
| communitys | Ͷ������ | List: Reference [Community](#community) |  |  | False |  |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |


# app

Ӧ��

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| name | ���� | String |  |  | True | None |  |
| cname | ������ | String |  |  | False |  |  |
| company | ��˾�� | String |  |  | False |  |  |
| ios_aid | �Ÿ� IOS accessid | Int |  |  | False | 0 |  |
| ios_skey | �Ÿ� IOS secretkey | String |  |  | False |  |  |
| android_aid | �Ÿ� Android accessid | Int |  |  | False | 0 |  |
| android_skey | �Ÿ� Android secretkey | String |  |  | False |  |  |
| sos_message_enable | Sos���ŷ��� | Boolean |  |  | False | False |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |


# auth

��������֤��Ϣ  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |


# bloodpressuredata

Ѫѹ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| dbp | ����ѹ | Int |  |  | False | 0 |  |
| sbp | ����ѹ | Int |  |  | False | 0 |  |


# cell

��վ��ʶ  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| mcc | MCC | String |  | 3 | False | 000 |  |
| mnc | MNC | String |  | 3 | False | 000 |  |
| lac | LAC | Int |  |  | False | 0 |  |
| cid | CELLID | Int |  |  | False | 0 |  |
| rssi | RSSI | Int |  |  | False | 0 |  |


# casepage

�û�����(��ʱ����)

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | ӵ���� | Reference: [Group](#group) |  |  | False | None |  |
| created_by | ������ | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| subject | ���� | String |  | 64 | False |  |  |
| type | ��Դ����(����) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | ���� | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | �� | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| user | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| happen_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| body | �������� | String |  | 4096 | False | None |  |


# community

����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| name | �������� | String |  |  | True | None |  |
| email | ��ҵ���� | Email |  | 64 | True | None |  |
| telephone | �ͷ��绰 | String |  | 15 | False |  |  |
| administrators | ��������Ա | List: Reference [Person](#person) |  |  | False |  |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |


# communityinvitemessage

����������Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | ���� | String |  | 128 | False |  |  |
| type | ��Ϣ���� | String |  | 16 | False | open | community_invite:�����������; community_join:�����������; community_leave:�����˳����� |
| sender | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | �������� | String |  |  | False |  |  |
| recipient | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| result | ������ | String |  | 16 | False | open | open:������; expired:����; cancel:ȡ��; accept:����; reject:�ܾ�; close:���� |
| accept_at | ����ʱ�� | DateTime |  |  | False | None |  |
| recipient_note | ���������� | String |  |  | False |  |  |
| community | ���� | Reference: [Community](#community) |  |  | False | None |  |


# communityjoinmessage

������������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | ���� | String |  | 128 | False |  |  |
| type | ��Ϣ���� | String |  | 16 | False | open | community_invite:�����������; community_join:�����������; community_leave:�����˳����� |
| sender | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | �������� | String |  |  | False |  |  |
| recipient | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| result | ������ | String |  | 16 | False | open | open:������; expired:����; cancel:ȡ��; accept:����; reject:�ܾ�; close:���� |
| accept_at | ����ʱ�� | DateTime |  |  | False | None |  |
| recipient_note | ���������� | String |  |  | False |  |  |
| community | ���� | Reference: [Community](#community) |  |  | False | None |  |


# communityleavemessage

�����뿪����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | ���� | String |  | 128 | False |  |  |
| type | ��Ϣ���� | String |  | 16 | False | open | community_invite:�����������; community_join:�����������; community_leave:�����˳����� |
| sender | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | �������� | String |  |  | False |  |  |
| recipient | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| result | ������ | String |  | 16 | False | open | open:������; expired:����; cancel:ȡ��; accept:����; reject:�ܾ�; close:���� |
| accept_at | ����ʱ�� | DateTime |  |  | False | None |  |
| recipient_note | ���������� | String |  |  | False |  |  |
| community | ���� | Reference: [Community](#community) |  |  | False | None |  |


# communitymessage

����ϵͳ��Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | ���� | String |  | 128 | False |  |  |
| type | ��Ϣ���� | String |  | 16 | False | open | community_invite:�����������; community_join:�����������; community_leave:�����˳����� |
| sender | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | �������� | String |  |  | False |  |  |
| recipient | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| result | ������ | String |  | 16 | False | open | open:������; expired:����; cancel:ȡ��; accept:����; reject:�ܾ�; close:���� |
| accept_at | ����ʱ�� | DateTime |  |  | False | None |  |
| recipient_note | ���������� | String |  |  | False |  |  |
| community | ���� | Reference: [Community](#community) |  |  | False | None |  |


# communitynotification

����֪ͨ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | False | None |  |
| title | ���� | String |  | 16 | True | None |  |
| content | ���� | String |  | 256 | True | None |  |
| group | �ؼ��� | Reference: [Group](#group) |  |  | False | None |  |
| recipient | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_cleared | ����� | Boolean |  |  | True | False |  |


# device

�豸��Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| did | �豸��� | String |  | 64 | True | None |  |
| alerts | ���� | List: Embedded [SettingAlert](#settingalert) |  |  | False |  |  |
| sos_numbers | ������� | List: Embedded [SettingSosNumber](#settingsosnumber) |  |  | False |  |  |
| sos_dial_cycle_times | �ֲ�����1-9 | Int |  |  | True | 1 | SOS�����Ժ󲦴�SOS�����ѭ������,9������ѭ�� |
| sos_sendmail | ���������Ƿ��Ͷ��� | Boolean |  |  | True | False | ���� |
| sos_readmail | �������ж����Ƿ��Զ����� | Boolean |  |  | True | False | ���� |
| sos_dial_cycle_mode | �ֲ�ģʽ | Int |  |  | True | 0 | 0��������SOS���룬1�ȴ�SOS�ٴ����ţ�2�Ȳ��������ٲ���SOS��3���������� |
| frequency_location | λ���ϱ�Ƶ�� | Int |  |  | True | 30 | ��λ���ӣ����������10min |
| frequency_step | �ǲ��ϱ�Ƶ�� | Int |  |  | True | 30 | ��λ���ӣ����������10mi |
| frequency_heartrate | �����ϱ�Ƶ�� | Int |  |  | True | 30 | ��λ���ӣ����������10mi |
| theshold_heartrate_h | �������� | Int |  |  | True | 140 |  |
| theshold_heartrate_l | �������� | Int |  |  | True | 40 |  |
| incoming_restriction | �������� | Boolean |  |  | True | False |  |
| bluetooth_enable | �������� | Boolean |  |  | True | False | ��������õ�Ѫѹ��ͬ������������ |
| bluetooth_devices | �����豸 | String |  | 256 | True |  | ��ʱ���� |
| profile | �龰ģʽ | Int |  |  | True | 0 | 0������1�𶯣�2��+������3����������S2ϵ�����𶯣������� |
| sleep_period_begin | ˯�߿�ʼʱ�� | String |  | 14 | True |  | ��ʽYYYYMMDDHHMMSS������YYYYMMDD����0��䣬ʵ��00000000083000,8��30am |
| sleep_period_end | ˯�߽���ʱ�� | String |  | 14 | True |  | ͬ�� |
| step_objective | �Ʋ�Ŀ�� | Int |  |  | True | 3000 |  |
| theshold_sit | �������� | Int |  |  | True | 60 |  |
| theshold_low_battery | �͵����� | Int |  |  | True | 20 |  |
| fences | ����Χ�� | List: Embedded [SettingFence](#settingfence) |  |  | False |  |  |
| pedometer_enable | �Ʋ����ݿ��� | Boolean |  |  | False | False |  |
| sleep_enable | ˯�����ݿ��� | Boolean |  |  | False | False |  |
| imei | �ƶ��豸ʶ���� | String |  | 16 | False |  |  |
| imsi | �ƶ��û�ʶ���� | String |  | 16 | False |  |  |
| type | �豸���� | String |  | 20 | False | BY102 |  |
| sim_phone | �ƶ��û����� | String |  | 16 | False |  |  |
| sim_phone_type | �ƶ��û������� | String |  | 8 | False | unicom | unicom:�й���ͨ; cmcc:�й��ƶ�; ctcc:�й����� |
| owner | ӵ���� | Reference: [Person](#person) |  |  | False | None |  |
| name | �豸���� | String |  | 32 | False |  |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| lastlogin_ip | ���������ַ | String |  | 16 | False |  |  |
| lastlogin_at | �������ʱ�� | DateTime |  |  | False | now() |  |
| active | ����״̬ | Boolean |  |  | True | False |  |
| active_at | �״μ���ʱ�� | DateTime |  |  | False | None |  |
| online | ����״̬ | Boolean |  |  | True | False |  |
| location_updated | ������� | Boolean |  |  | True | False |  |
| location_updated_at | �������ʱ�� | DateTime |  |  | True |  |  |
| last_location | �������� | Point |  |  | True |  |  |
| last_city | ���� | String |  |  | True |  |  |
| last_address | ��ַ | String |  |  | True |  |  |
| wear_flag | ���״̬ | Int |  |  | False | None |  |
| wear_updated_at | ���״̬����ʱ�� | DateTime |  |  | False | None | 0δ�����1����������ڲ������ʵ�ʱ�����״̬���ն��Լ������������ |
| remaining_power | ʣ�����(%�� | Int |  |  | False | 0 |  |
| remaining_power_updated_at | ����״̬����ʱ�� | DateTime |  |  | False | None |  |
| wifi | WIFI | List: Embedded [WIFI](#wifi) |  |  | False |  |  |
| wifi_updated_at | WIFI����ʱ�� | DateTime |  |  | False | None |  |
| software_version | ����汾 | String |  | 48 | False |  |  |
| iccid1 | �ƶ��û�iccid��1 | String |  | 21 | False | None |  |
| iccid2 | �ƶ��û�iccid��2 | String |  | 21 | False | None |  |
| fence_notification_updated_at | Χ��֪ͨ����ʱ�� | DateTime |  |  | False | None |  |
| service_number | ����� | String |  | 32 | False | None | ��ʱ���� |
| fall_model | ����ģʽ���� | String |  |  | False | 0 | 0�޶��š��绰 1������ 2���绰 3����+�绰�������������ֻ��� |
| fall_enable | �����жϿ��� | Boolean |  |  | False | 0 | �����������ֻ��� |
| track_enable | �켣���� | Boolean |  |  | False | 0 | �����S2����λ���� |



# devicetoken

�ն˱�ʶ  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| token_type | �豸���� | String |  | 10 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | True | None |  |
| is_enable_aliase | �����Ƿ���� | Boolean |  |  | True | False |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |


# emailconfirm

Emailȷ��

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| person | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| email | ע������ | Email |  | 64 | True | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| send_at | ����ʱ�� | DateTime |  |  | False | None |  |
| send_ok | ���ͽ�� | Boolean |  |  | False | None |  |
| send_error | ʧ����Ϣ | String |  |  | False | None |  |
| accept_at | ȷ��ʱ�� | DateTime |  |  | False | None |  |


# expertpage

ר����Դ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | ӵ���� | Reference: [Group](#group) |  |  | False | None |  |
| created_by | ������ | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| subject | ���� | String |  | 64 | False |  |  |
| type | ��Դ����(����) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | ���� | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | �� | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| is_published | �Ƿ񷢲� | Boolean |  |  | False | True |  |
| body | �������� | String |  | 4096 | False | None |  |
| filename | ͼƬ�ļ��� | String |  | 64 | False | None |  |
| media_length | �ļ����� | Int |  |  | False | 0 |  |
| url | ͼƬ���ص�ַ | String |  | 128 | False | None |  |
| thumb_url | ����ͼ���ص�ַ | String |  | 128 | False | None |  |


# group

����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| owner | ӵ���� | Reference: [Person](#person) |  |  | True | None |  |
| name | ������ | String |  |  | True |  |  |
| community | ���� | Reference: [Community](#community) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| is_public | �Ƿ񹫿� | Boolean |  |  | False | False |  |
| members | ��Ա�б� | List: [Member](#member) |  |  | |  |  |


# groupinvitecode

С��������Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| date | ���� | String |  | 16 | True |  |  |
| code | ������ | String |  | 6 | True |  |  |
| target | Ŀ���û� | String |  |  | False | None |  |
| group | ������ | Reference: [Group](#group) |  |  | False | None |  |
| created_by | ������ | Reference: [Person](#person) |  |  | False | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| is_confirmed | ��ȷ�� | Boolean |  |  | True | False |  |
| confirmed_by | ȷ���û� | Reference: [Person](#person) |  |  | False | None |  |
| confirmed_at | ȷ��ʱ�� | DateTime |  |  | False | None |  |


# groupnotification

��ͥȦ֪ͨ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | False | None |  |
| title | ���� | String |  | 16 | True | None |  |
| content | ���� | String |  | 256 | True | None |  |
| group | �ؼ��� | Reference: [Group](#group) |  |  | False | None |  |
| recipient | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_cleared | ����� | Boolean |  |  | True | False |  |
| member | ��Ա | Reference: [Person](#person) |  |  | False | None |  |
| action | �¼� | String |  |  | True |  |  |


# heartratedata

��������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| heartrate | ���� | Int |  |  | False | 0 |  |


# heartratenotification

�����쳣֪ͨ��Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | False | None |  |
| title | ���� | String |  | 16 | True | None |  |
| content | ���� | String |  | 256 | True | None |  |
| group | �ؼ��� | Reference: [Group](#group) |  |  | False | None |  |
| recipient | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_cleared | ����� | Boolean |  |  | True | False |  |
| data | ���� | Reference: [HeartRateData](#heartratedata) |  |  | True | None |  |


# imei

IMEI����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| imei | �ƶ��豸ʶ���� | String |  | 15 | True | None |  |
| deviceid | �豸���к� | String |  | 20 | False | None |  |
| iccid | �ƶ��û�iccid�� | String |  | 64 | False | None |  |
| update_at | ����ʱ�� | DateTime |  |  | False | now() |  |


# locationcache

����λ�û���

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| _id | id | String |  | 64 | True | None |  |
| cells | ��ַ | String |  | 2048 | False | None |  |
| country | ���� | String |  | 32 | False | None |  |
| region | ʡ�� | String |  | 32 | False | None |  |
| city | ���� | String |  | 32 | False | None |  |
| county | ���� | String |  | 32 | False | None |  |
| street | �ֵ� | String |  | 32 | False | None |  |
| street_number | �ֵ��� | String |  | 32 | False | None |  |
| address | ��ַ | String |  | 512 | False | None |  |
| point | ���� | Point |  |  | False | None |  |
| accuracy | ���� | Int |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |


# locationdata

��λ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| type | ���� | String |  |  | False | 0 | 0:Gps��λ; 1:��վ��λ |
| is_reply | �Ƿ�Ϊ��Ӧ | Boolean |  |  | False | False |  |
| city | ���� | String |  | 16 | False |  |  |
| address | ��ַ | String |  | 128 | False |  |  |
| point | ���� | Point |  |  | False | None |  |
| cell | CELL | List: Embedded [CELL](#cell) |  |  | False |  |  |
| wifi | WIFI | List: Embedded [WIFI](#wifi) |  |  | False |  |  |


# locationnotification

λ���쳣֪ͨ��Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | False | None |  |
| title | ���� | String |  | 16 | True | None |  |
| content | ���� | String |  | 256 | True | None |  |
| group | �ؼ��� | Reference: [Group](#group) |  |  | False | None |  |
| recipient | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_cleared | ����� | Boolean |  |  | True | False |  |
| data | λ�� | Reference: [LocationData](#locationdata) |  |  | True | None |  |


# mediadata

ͨ��upload�ϴ���ý������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| media_id | ý���� | Int |  |  | False | 0 |  |
| media_type | ý������ | Int |  |  | False | 0 |  |
| media_dest | Ŀ�� | Int |  |  | False | 0 |  |
| media_length | ���� | Int |  |  | False | 0 |  |
| media_file | �ļ��� | String |  |  | False |  |  |


# mediamessage

ý����Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | ���� | String |  | 64 | False |  |  |
| sender | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| recipient | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| send_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| send_by | �����ն� | String |  | 64 | False |  |  |
| read_at | ��ȡʱ�� | DateTime |  |  | False | None |  |
| sender_deleted | ������ɾ�� | Boolean |  |  | False | False |  |
| sender_deleted_at | ������ɾ��ʱ�� | DateTime |  |  | False | None |  |
| recipient_deleted | ������ɾ�� | Boolean |  |  | False | False |  |
| recipient_deleted_at | ������ɾ��ʱ�� | DateTime |  |  | False | None |  |
| media_type | ���� | Int |  |  | False | 0 |  |
| media_length | ���� | Int |  |  | False | 0 |  |
| filename | �ļ��� | String |  | 64 | False | None |  |
| url | ���ص�ַ | String |  | 128 | False | None |  |


# mediapage

ý����Դ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | ӵ���� | Reference: [Group](#group) |  |  | False | None |  |
| created_by | ������ | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| subject | ���� | String |  | 64 | False |  |  |
| type | ��Դ����(����) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | ���� | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | �� | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| media_length | ���� | Int |  |  | False | 0 |  |
| filename | �ļ��� | String |  | 64 | False | None |  |
| url | ���ص�ַ | String |  | 128 | False | None |  |
| thumb_url | ����ͼ���ص�ַ | String |  | 128 | False | None |  |
| upload_type | �ϴ����� | Int |  |  | False | 0 |  |
| devices | �������豸�б� | List: Reference [Device](#device) |  |  | False |  |  |
| devices_finished | �ѷ����豸�б� | List: Reference [Device](#device) |  |  | False |  |  |


# member

С���Ա

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | �� | Reference: [Group](#group) |  |  | True | None |  |
| person | ��Ա | Reference: [Person](#person) |  |  | True | None |  |
| member_name | ��ϵ | String |  |  | False |  |  |
| is_default | ��ȱʡ�� | Int |  |  | False | 0 |  |


# message

������Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | ���� | String |  | 64 | False |  |  |
| sender | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| recipient | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| send_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| send_by | �����ն� | String |  | 64 | False |  |  |
| read_at | ��ȡʱ�� | DateTime |  |  | False | None |  |
| sender_deleted | ������ɾ�� | Boolean |  |  | False | False |  |
| sender_deleted_at | ������ɾ��ʱ�� | DateTime |  |  | False | None |  |
| recipient_deleted | ������ɾ�� | Boolean |  |  | False | False |  |
| recipient_deleted_at | ������ɾ��ʱ�� | DateTime |  |  | False | None |  |


# msgnotification

Message֪ͨ��Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | False | None |  |
| title | ���� | String |  | 16 | True | None |  |
| content | ���� | String |  | 256 | True | None |  |
| group | �ؼ��� | Reference: [Group](#group) |  |  | False | None |  |
| recipient | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_cleared | ����� | Boolean |  |  | True | False |  |
| page | Page | Reference: [MediaPage](#mediapage) |  |  | True | None |  |


# notification

����֪ͨ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | False | None |  |
| title | ���� | String |  | 16 | True | None |  |
| content | ���� | String |  | 256 | True | None |  |
| group | �ؼ��� | Reference: [Group](#group) |  |  | False | None |  |
| recipient | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_cleared | ����� | Boolean |  |  | True | False |  |


# notificationservice

���ͷ���

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| name | ������ | String |  | 16 | True | aiqiangua |  |
| accessid | accessid | Int |  |  | True | 0 |  |
| secretkey | secretkey | String |  |  | True |  |  |


# page

��Դ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | ӵ���� | Reference: [Group](#group) |  |  | False | None |  |
| created_by | ������ | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| subject | ���� | String |  | 64 | False |  |  |
| type | ��Դ����(����) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | ���� | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | �� | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |


# pagecomment

����  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| created_by | ������ | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| comment_id | �ڲ���� | String |  |  | False | None |  |
| content | �ظ� | String |  | 256 | False |  |  |


# pagestar

����  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| created_by | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |


# passwordresetnotify

Email��������֪ͨ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| person | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| email | ע������ | Email |  | 64 | True | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| send_at | ����ʱ�� | DateTime |  |  | False | None |  |
| send_ok | ���ͽ�� | Boolean |  |  | False | None |  |
| send_error | ʧ����Ϣ | String |  |  | False | None |  |
| accept_at | ȷ��ʱ�� | DateTime |  |  | False | None |  |
| password | �û����� | String |  | 64 | True | None |  |


# passwordresetrequest

Email��������ȷ��

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| person | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| email | ע������ | Email |  | 64 | True | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| send_at | ����ʱ�� | DateTime |  |  | False | None |  |
| send_ok | ���ͽ�� | Boolean |  |  | False | None |  |
| send_error | ʧ����Ϣ | String |  |  | False | None |  |
| accept_at | ȷ��ʱ�� | DateTime |  |  | False | None |  |


# pedometerdata

�Ʋ�����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| value | �ۼƲ��� | Int |  |  | False | 0 |  |


# person

��Ա��Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| username | �û��� | String |  | 16 | True | None |  |
| password | �û����� | String |  | 64 | True | None |  |
| email | ע������ | Email |  | 64 | False | None |  |
| nickname | ���� | String |  | 64 | False | None |  |
| phone | �ֻ����� | String |  | 15 | False | None |  |
| telephone | �绰���� | String |  | 15 | False | None |  |
| app | ������ | String |  | 30 | True | aiqiangua | ��ʶ��½��app |
| devicetokens | �ն˱�ʶ�б� | List: Embedded [DeviceToken](#devicetoken) |  |  | False |  |  |
| weight | ���أ�KG�� | Int |  |  | False | 0 |  |
| step | ������CM�� | Int |  |  | False | 0 |  |
| age | ���䣨�꣩ | Int |  |  | False | 0 |  |
| height | ��ߣ�CM�� | Int |  |  | False | 0 |  |
| avatar | ͷ���ļ� | String |  |  | False | None |  |
| avatar_url | ͷ�� | String |  |  | False | /media/avatar/200/male.png |  |
| community | ���� | Reference: [Community](#community) |  |  | False | None |  |
| role | ��ɫ | String |  | 10 | True | user | user:�û�; operator:����Ա; superuser:��������Ա |
| gender | �Ա� | String |  | 10 | True | male | male:�� ; female:Ů |
| address | ��ַ | String |  | 64 | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| lastlogin_ip | �����¼��ַ | String |  | 16 | False | None |  |
| lastlogin_at | �����¼ʱ�� | DateTime |  |  | False | None |  |
| lastlogin_by | ��¼�豸 | String |  |  | True |  |  |
| enable | ���� | Boolean |  |  | False | False | ��ʱû��ʹ�� |
| email_is_checked | ��������֤ | Boolean |  |  | False | False |  |
| phone_is_checked | �ֻ�����֤ | Boolean |  |  | False | False |  |
| push_sos_enable | ����SOS���� | Boolean |  |  | False | False |  |
| push_fence_enable | �������Χ������ | Boolean |  |  | False | False |  |
| push_abnormal_enable | �������������� | Boolean |  |  | False | False |  |
| push_message_enable | �����ͥȦ��Ϣ���� | Boolean |  |  | False | False |  |
| push_lowpower_enable | ����͵����� | Boolean |  |  | False | False |  |
| push_system_enable | ����ϵͳ��Ϣ���� | Boolean |  |  | False | False |  |
| auth_type | ��Ȩ���� | String |  | 10 | False | None | weibo:weibo; qq:qq; weixin:weixin |
| auth_uid | ��ȨΨһ��ʶ | String |  | 256 | False | None |  |
| auth_updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| home | Home | String |  |  | False | None |  |
| home_wifi | Home Wifi | String |  | 32 | False | None |  |
| devices | �豸�б� | List: [Device](#device) |  |  | |  |  |
| groups | С���б� | List: [Group](#group) |  |  | |  |  |


# posturedata

��������(����)

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| posture_type | �������� | Int |  |  | False | 0 |  |
| abnormal_count | �쳣���� | Int |  |  | False | 0 |  |
| count | ���� | Int |  |  | False | 0 |  |
| calorie | ���Ŀ�·�� | Int |  |  | False | 0 |  |


# powerdata

��������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| type | ��/�ػ����� | String |  |  | False | 0 | 0:����; 1:�ػ�; 2:�����ϱ�; 3:�͵�֪ͨ |
| remaining_power | ʣ�����(%�� | Int |  |  | False | 0 |  |
| location | �͵�ʱλ�� | Reference: [LocationData](#locationdata) |  |  | False | None |  |


# powernotification

�͵�֪ͨ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | False | None |  |
| title | ���� | String |  | 16 | True | None |  |
| content | ���� | String |  | 256 | True | None |  |
| group | �ؼ��� | Reference: [Group](#group) |  |  | False | None |  |
| recipient | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_cleared | ����� | Boolean |  |  | True | False |  |
| data | ��Դ���� | Reference: [PowerData](#powerdata) |  |  | True | None |  |


# registerrequest

Emailע��ȷ��

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| person | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| email | ע������ | Email |  | 64 | True | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| send_at | ����ʱ�� | DateTime |  |  | False | None |  |
| send_ok | ���ͽ�� | Boolean |  |  | False | None |  |
| send_error | ʧ����Ϣ | String |  |  | False | None |  |
| accept_at | ȷ��ʱ�� | DateTime |  |  | False | None |  |


# rfiddata

��������(����)

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| state | ���� | Int |  |  | False | 0 |  |


# sedentarydata

��������(����)

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| value | ����ʱ�� | Int |  |  | False | 0 |  |


# servicepage

�û�����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | ӵ���� | Reference: [Group](#group) |  |  | False | None |  |
| created_by | ������ | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| subject | ���� | String |  | 64 | False |  |  |
| type | ��Դ����(����) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | ���� | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | �� | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| user | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| body | �������� | String |  | 4096 | False | None |  |
| is_closed | �Ƿ�ر� | Boolean |  |  | False | False |  |


# settingalert

�¼�����  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| seqid | ��� | Int |  |  | True | None |  |
| enable | ���� | Boolean |  |  | True | False |  |
| is_medicine | ��ҩ | Boolean |  |  | True | False | ������app��ʶ����ʵ������ |
| name | ���� | String |  | 40 | True |  |  |
| alert_type | �������� | Int |  |  | True | 1 | 0�����������ѣ������ֻ��������������� 1��һ�������ѣ��趨���� |
| cycle | ���� | Int |  |  | True | 1 | 1��������Ϊ���ڣ���Ӧ�����0,2��������Ϊ���ڣ���Ӧ�����1 |
| time | ʱ�� | String |  | 14 | False |  | ��alert_type=0ʱ����ʽΪ 1001101+21+30+ �����壺ǰ7λ��Ӧ���ա���һ������������Ҫ���ѵ���Щ�죬������HHMM���м���+�ŷָ�ͽ�β����alert_type=1ʱ����ʽΪYYYYMMDDHHMMSS 20150313213000 |
| media_length | �����ļ����� | Int |  |  | False | 0 | �ϴ�ǰ�����ļ���С����󲻵ó���10KB��������5K~8K֮�䣬����ᱨ������Ҫ����������������������� |
| file_checksum | �����ļ���У��ͣ� | Int |  |  | False | 0 | ���������� |
| filename | �����ļ��� | String |  | 64 | False | None |  |
| url | ���ص�ַ | String |  | 128 | False | None | ���������� |
| created_at | ����ʱ�� | DateTime |  |  | False | None |  |


# settingfence

Χ��  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| seqid | ��� | Int |  |  | True | None |  |
| freq | ÿ�� | Boolean |  |  | False | True |  |
| enable | ���� | Boolean |  |  | True | False |  |
| name | ���� | String |  | 40 | True |  |  |
| time_begin | ��ʼʱ�� | Int |  |  | True | 0 |  |
| time_end | ��ֹʱ�� | Int |  |  | True | 0 |  |
| safe_area | ��ȫ���� | Polygon |  |  | False | None |  |


# settingsosnumber

�������  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| seqid | ��� | Int |  |  | True | None |  |
| name | ���� | String |  | 32 | True |  |  |
| num | ���� | String |  | 16 | True |  |  |
| dial_flag | �Ƿ���� | Boolean |  |  | True | False | �Ƿ������������ΪSOS���룬�����豸SOSʱ���벦��ѭ�� |


# shortmessage

���ŷ�������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_confirmed | ��ȷ�� | Boolean |  |  | True | False |  |
| phone | �ֻ����� | String | 11 | 11 | True | None |  |
| content | �������� | String |  | 160 | True | None |  |


# shortmessagechecksum

������֤�뷢������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_confirmed | ��ȷ�� | Boolean |  |  | True | False |  |
| phone | �ֻ����� | String | 11 | 11 | True | None |  |
| content | �������� | String |  | 160 | True | None |  |
| purpose | ��; | String |  | 16 | True | login | login:��̬����; reset:��������; register:ע��; password:�ѷ��� |
| host_ip | ����IP | String |  | 16 | True |  |  |
| checksum | ��֤�� | String |  | 6 | True | None |  |


# shortmessagesos

���ȶ��ŷ�������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_confirmed | ��ȷ�� | Boolean |  |  | True | False |  |
| phone | �ֻ����� | String | 11 | 11 | True | None |  |
| content | �������� | String |  | 160 | True | None |  |


# simphone

SIM����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| iccid | �ƶ��û�iccid�� | String |  | 64 | True | None |  |
| sim_phone | �ƶ��û����� | String |  | 16 | False | None |  |
| sim_phone_type | �ƶ��û������� | String |  | 8 | False | unicom | unicom:�й���ͨ; cmcc:�й��ƶ�; ctcc:�й����� |
| update_at | ����ʱ�� | DateTime |  |  | False | now() |  |


# sleepdata

˯������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| time_end | ��ֹʱ�� | DateTime |  |  | False | None |  |
| interval | ����� | Int |  |  | False | 30 |  |
| total | ������ | Int |  |  | False | 0 |  |
| data | ˯������ | List: Embedded [SleepDataSleep](#sleepdatasleep) |  |  | False |  | ��48�飬��Сʱ1�飬(0,0)������������ݣ���һ�����ݵĿ�ʼʱ����time_begin |


# sleepdatasleep

����  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| turn_over | ����� | Int |  |  | False | 0 | ����255����stateΪ0ʱ�����ѣ�turn_over=0,state=2���������ִ��ڻ����3��ʱ��������˯��״̬ |
| state | ˯������ | Int |  |  | False | 0 | state=0��ǳ˯�� 1 �ж�˯�ߣ� 2 ���˯�� |

# sosdata

��������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| type | ���� | String |  |  | False | 0 | 0:Gps��λ; 1:��վ��λ |
| city | ���� | String |  | 16 | False |  |  |
| address | ��ַ | String |  | 128 | False |  |  |
| point | ���� | Point |  |  | False | None |  |
| cell | CELL | List: Embedded [CELL](#cell) |  |  | False |  |  |
| wifi | WIFI | List: Embedded [WIFI](#wifi) |  |  | False |  |  |
| heartrate | ����ֵ | Int |  |  | False | None |  |
| is_removed | �Ƿ����� | Boolean |  |  | False | False |  |


# sosnotification

Sos֪ͨ��Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | �ն����� | String |  | 16 | True | ios | ios:ios; android:android |
| token | �豸��ʶ | String |  | 128 | False | None |  |
| title | ���� | String |  | 16 | True | None |  |
| content | ���� | String |  | 256 | True | None |  |
| group | �ؼ��� | Reference: [Group](#group) |  |  | False | None |  |
| recipient | ������ | Reference: [Person](#person) |  |  | True | None |  |
| created_at | �ύʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| expired_at | ����ʱ�� | DateTime |  |  | True |  |  |
| sched_send_at | Ԥ�ڷ���ʱ�� | DateTime |  |  | True | now() |  |
| error_code | ������ | Int |  |  | False | None |  |
| error_info | ������Ϣ | String |  |  | False | None |  |
| is_completed | ����� | Boolean |  |  | True | False |  |
| is_cleared | ����� | Boolean |  |  | True | False |  |
| data | SOS | Reference: [SosData](#sosdata) |  |  | True | None |  |


# sysmessage

ϵͳ��Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | ���� | String |  | 128 | False |  |  |
| type | ��Ϣ���� | String |  | 16 | False | open | community_invite:�����������; community_join:�����������; community_leave:�����˳����� |
| sender | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | �������� | String |  |  | False |  |  |
| recipient | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| result | ������ | String |  | 16 | False | open | open:������; expired:����; cancel:ȡ��; accept:����; reject:�ܾ�; close:���� |
| accept_at | ����ʱ�� | DateTime |  |  | False | None |  |
| recipient_note | ���������� | String |  |  | False |  |  |


# textmessage

�ı���Ϣ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | ���� | String |  | 64 | False |  |  |
| sender | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| recipient | �����û� | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| send_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| send_by | �����ն� | String |  | 64 | False |  |  |
| read_at | ��ȡʱ�� | DateTime |  |  | False | None |  |
| sender_deleted | ������ɾ�� | Boolean |  |  | False | False |  |
| sender_deleted_at | ������ɾ��ʱ�� | DateTime |  |  | False | None |  |
| recipient_deleted | ������ɾ�� | Boolean |  |  | False | False |  |
| recipient_deleted_at | ������ɾ��ʱ�� | DateTime |  |  | False | None |  |
| body | ���� | String |  | 256 | False | None |  |


# textpage

�ı���Դ

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | ӵ���� | Reference: [Group](#group) |  |  | False | None |  |
| created_by | ������ | Reference: [Person](#person) |  |  | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| subject | ���� | String |  | 64 | False |  |  |
| type | ��Դ����(����) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | ���� | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | �� | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| body | ���� | String |  | 4096 | False | None |  |


# uploadfile

�ļ�����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| notes | ��ע | String |  |  | False | None |  |
| type | ���� | String |  |  | False | None |  |
| url | ���ص�ַ | String |  | 128 | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | False | now() |  |
| result | ������ | String |  |  | False | None |  |
| detail | �쳣��� | String |  |  | False | None |  |
| filename | �ļ��� | String |  | 64 | False | None |  |


# wifi

��վ��ʶ  -- ��Ƕ����

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| addr | ADDR | String |  | 32 | False |  |  |
| ssid | SSID | String |  | 32 | False |  |  |
| rssi | RSSI | Int |  |  | False | 0 |  |


# weardata

�������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | �û� | Reference: [Person](#person) |  |  | False | None |  |
| device | �豸 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | ��¼ʱ�� | DateTime |  |  | False | now() |  |
| time_begin | ����ʱ�� | DateTime |  |  | False | None |  |
| flag | ״̬ | Int |  |  | False | 0 |  |


# weathercache

��������

| �ֶ��� | ˵�� | ���� | ��С���� | ��󳤶� | �����ֶ� | ȱʡֵ | ��ע |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| key | key | String |  | 64 | True | None |  |
| city | ���� | String |  | 16 | False | None |  |
| date | ���� | String |  | 16 | False | None |  |
| weather_id | ������� | Int |  |  | False | 0 |  |
| weather_desc | �������� | String |  | 24 | False |  |  |
| pm25 | ��ǰph25ֵ | Int |  |  | False | 25 |  |
| temp_now | ��ǰ�¶� | Int |  |  | False | 25 |  |
| temp_low | ������� | Int |  |  | False | 25 |  |
| temp_high | ������� | Int |  |  | False | 25 |  |
| t_weather_id | ����������� | Int |  |  | False | 0 |  |
| t_weather_desc | ������������ | String |  | 24 | False |  |  |
| t_temp_low | ������� | Int |  |  | False | 25 |  |
| t_temp_high | ������� | Int |  |  | False | 25 |  |
| advice | ���½��� | String |  | 256 | False | None |  |
| created_at | ����ʱ�� | DateTime |  |  | True | now() |  |
| updated_at | ����ʱ�� | DateTime |  |  | True | now() |  |