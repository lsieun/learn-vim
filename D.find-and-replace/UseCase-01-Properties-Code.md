# Properties -> Java Code

Java Code:

```java
public class URLConfig {

    public static final String API_KEY;
    public static final String APP_ID;
    public static final String APP_SECRET;

    static {
        InputStream in = null;
        Properties prop = new Properties();
        prop.load(in);

        API_KEY = prop.getProperty("API_KEY", "");
        APP_ID = prop.getProperty("APP_ID", "");
        APP_SECRET = prop.getProperty("APP_SECRET", "");
    }
}
```

Property File

```txt
#######################基础平台生产秘钥###########################
#生产秘钥
API_KEY = 4146e172
APP_ID = 2dd1ec480fab08f7509cf10
APP_SECRET = 7682fc21519c618059b
```

## 完整的配置文件

```txt
#######################基础平台生产秘钥###########################
#生产秘钥
API_KEY = 4146e172
APP_ID = 2dd1ec480fab08f7509cf10
APP_SECRET = 7682fc21519c618059b
#######################基础平台接口地址###########################
#Token获取接口  
GET_TOKEN = http://10.60.1.68:18080/apiman-gateway/r93535Test.com/gettoken/1.0
#获取登录用户   sessionid  tocken apikey
AUTHINFO_SERVICE_GETLOGINUSER = http://10.60.1.68:18080/apiman-gateway/r93535Test.com/authInfoServicegetLoginUser/1.0
#根据人员ID获取人员信息
GET_USER_BY_ID = http://10.60.1.68:18080/apiman-gateway/r93535Test.com/usersgetUserById/1.0
#根据人员account信息获取人员信息
GET_USERINFO_BYACCOUNT = http://10.60.1.68:18080/apiman-gateway/r93535Test.com/usersgetUserByAccount/1.0
#根据人员ID获取能看见的工区信息
GET_PROJECT_AREA_BY_USER_ID = http://10.60.1.68:18080/apiman-gateway/r93535Test.com/usersgetProjectAreaByUserId/1.0
#根据父部门节点获取所有子部门信息
#GET_ALL_DEPARTMENTS = http://10.60.1.68:18080/apiman-gateway/r93535Test.com/departmentsgetAllDepartments/1.0
#GET_ALL_DEPARTMENTS = http://192.168.96.11:8080/apiman-gateway/base/departmentsgetAllDepartments/1.0
#GET_ALL_DEPARTMENTS = http://10.60.1.247:8080/apiman-gateway/base/departmentsgetAllDepartments/1.0
GET_ALL_DEPARTMENTS = http://10.30.1.9:9300/servicesapitest/departments/getAllDepartments
#GET_ALL_DEPARTMENTS = http://10.1.0.101:9300/servicesapi/departments/getAllDepartments
#根据部门ID获取该部门下的人员信息
GET_ALL_USERS_BYDEPTID = http://10.60.1.68:18080/apiman-gateway/r93535Test.com/departmentsgetAllUsersByDeptId/1.0
#根据项目ID获取项目基础信息                                                                
GET_PROJECTINFO_BY_ID = http://10.60.1.247:8080/apiman-gateway/base/projectInfogetProjectInfoById/1.0
#获取所有项目
GET_ALL_PROJECT_INFOS = http://10.1.0.65/servicesapi/projectInfo/getAllProjectInfos
#根据标段ID获取工区信息
#GET_PROJECT_AREA_BY_SECTION_ID = http://10.30.1.9:9300/servicesapitest/projectSection/getProjectAreaList
GET_PROJECT_AREA_BY_SECTION_ID = http://10.1.0.65/servicesapi/projectSection/getProjectAreaList
#根据人员ID获取所在的部门类型
GET_JS_DEPTS_BY_USER_ID = http://10.60.1.247:8080/apiman-gateway/base/usersgetJSDeptsByUserId/1.0
#根据人员ID获取能看见的项目
GET_PROJECT_INFO_BY_USER_ID = http://10.60.1.247:8080/apiman-gateway/base/usersgetProjectinfoByUserId/1.0
#根据项目id获取对应的标段
GET_PROJECTSECTION_BY_INFOID = http://10.60.1.247:8080/apiman-gateway/base/projectInfogetProjectSectionByInfoId/1.0
#根据项目id获取对应的构筑物
GET_BUILDS_BY_PROJECT_ID = http://10.1.0.65/servicesapi/projectInfo/getBuilds
#根据人员id获取能看见的标段
GET_PROJECT_SECTION_BY_USER_ID = http://10.1.0.153/servicesapi/users/getProjectSectionByUserId
#GET_PROJECT_SECTION_BY_USER_ID = http://10.30.1.9:9500/servicesapitest/users/getBuildStationSectionByUserId
#根据标段ID获取构筑物 /标段id/构筑物id
#GET_BUILD_LIST_BY_PROJECTSECTION = http://10.30.1.9:9300/servicesapitest/projectSection/getBuildList
GET_BUILD_LIST_BY_PROJECTSECTION = http://10.1.0.65/servicesapi/projectSection/getBuildList
#根据标段ID获取工点信息
GET_SECTION_BY_PROJECTSECTION = http://10.60.1.247:8080/apiman-gateway/base/projectSectiongetProjectSiteList/1.0
#获取所有片区
CATE_GORY_ITEMS = http://10.1.0.65/servicesapi/categoryItems/getCategoryItems
#获取项目结构树
FIND_DIRECTORY_TREELIST = http://10.60.1.85:8080/zwzf/api/directoryTree/findTreelist
#获取检验批数据
GET_JYP_BYBBSID_PAGE = http://cars.crbim.win/jypapi/JypApi/getJypByBbsIdPage

#检验批预览
JYP_URL=http://cars.crbim.win/jypapi/JypApi/loadPdfFile

#检验批appid
JYP_APPID=1508296151075141
#\u83B7\u53D6\u6784\u7B51\u7269\u4FE1\u606F\u5217\u8868
GET_BUILD_BY_ID=http://10.30.1.9:9500/servicesapitest/build/getBuildInfoByBuildId
#\u83B7\u53D6\u56FE\u7247
GET_BUILD_IMAGE=http://10.30.1.9:9990/baseservicetest/rest/copyFiles.action
```

操作：

- 第一步，删除以`#`开头的行：`:g/^#/d`
- 第二步，删除空行：`:g/^[ ^I]*$/d`，其中`^I`是`Tab`按键
- 第三步，删除`=`号之后的数据：`:%s/^\(.*\)=.*/\1/g`
- 第四步，删除行尾的空格：`:%s/^\(.*\)  */\1/g`
- 第五步，生成Java语句`public static final String API_KEY;`：`:%s/^\(.*\)/public static final String \1;/g`
- 第六步，生成Java语句`API_KEY = prop.getProperty("API_KEY", "");`：`:%s/^\(.*\)$/\1 = prop.getProperty("\1", "");/g`
