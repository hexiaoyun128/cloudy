# 用例xml约束文件

为了更方便的编写测试用例，使用了xsd文件来约束测试用例的编写，xsd文件内容和关键说明如下：

文件链接 [/ce-shi/jie-kou-zi-dong-hua-ce-shi/test\_case.xsd](/ce-shi/jie-kou-zi-dong-hua-ce-shi/test_case.xsd "test\_case.xsd")

```
<?xml version="1.0" ?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"
    targetNamespace="http://www.gachain.org"
    xmlns="http://www.hechihan.com"
    elementFormDefault="qualified">
    <xs:element name="test_case" >
        <xs:complexType >
            <xs:all>
                <xs:element  name="case_api">
                    <xs:complexType>
                        <xs:sequence>
                            <!--测试用例名称-->
                            <xs:element name="case_name" type="xs:string"/>
                            <!--测试用例使用的用户，用于支持多用户，对于登录测试用户默认为:none-->
                            <xs:element name="case_user" type="xs:string"/>
                            <!--用例所属大类或者服务-->
                            <xs:element name="case_category" type="xs:string"/>
                            <!--用例所属模块-->
                            <xs:element name="case_module" type="xs:string"/>
                            <!--用例测试功能点-->
                            <xs:element name="case_function" type="xs:string"/>
                            <!--测试用例是否有效-->
                            <xs:element name="case_active" type="xs:boolean" default="true"/>
                            <!--当前测试用例是否开启debug-->
                            <xs:element name="case_debug" type="xs:boolean" default="true"/>
                            <!--请求地址，基地址在配置文件中配置-->
                            <xs:element name="case_address" type="xs:string"/>
                            <!--请求方法-->
                            <xs:element name="case_method" >
                                <xs:simpleType>
                                    <xs:restriction base="xs:string">
                                        <xs:enumeration value="post"/>
                                        <xs:enumeration value="get"/>
                                        <xs:enumeration value="put"/>
                                        <xs:enumeration value="delete"/>
                                    </xs:restriction>
                                </xs:simpleType>
                            </xs:element>
                            <!--请求数据类型-->
                            <xs:element name="case_data_type" >
                                <xs:simpleType>
                                    <xs:restriction base="xs:string">
                                        <xs:enumeration value="Form"/>
                                        <xs:enumeration value="Json"/>
                                    </xs:restriction>
                                </xs:simpleType>
                            </xs:element>
                            <!--测试用例检查点，用于判断功能是否满足需要-->
                            <xs:element name="case_check_point">
                                <xs:simpleType>
                                    <xs:restriction base="xs:string">
                                        <!--包含-->
                                        <xs:enumeration value="contain"/>
                                        <!--不包含要-->
                                        <xs:enumeration value="notcontain"/>
                                        <!--等于-->
                                        <xs:enumeration value="eq"/>
                                        <!--不等于-->
                                        <xs:enumeration value="noteq"/>
                                        <!--正则，暂不支持-->
                                        <xs:enumeration value="regex"/>
                                    </xs:restriction>
                                </xs:simpleType>
                            </xs:element>
                            <!--测试用例检查内容-->
                            <xs:element name="case_check_content" >
                                <xs:simpleType>
                                    <xs:restriction base="xs:string">
                                        <xs:whiteSpace value="replace"/>
                                    </xs:restriction>
                                </xs:simpleType>
                            </xs:element>
                            <!--请求数据，在用例中为json数据-->
                            <xs:element name="case_request_data">
                                <xs:simpleType>
                                    <xs:restriction base="xs:string">
                                        <xs:whiteSpace value="replace"/>
                                    </xs:restriction>
                                </xs:simpleType>
                            </xs:element>
                            <!--测试用例说明-->
                            <xs:element name="case_comment" type="xs:string"  />
                        </xs:sequence>
                    </xs:complexType>
                </xs:element>
            </xs:all>
        </xs:complexType>
    </xs:element>
</xs:schema>
```

请求参数中保留字段为:

local\_file\_data:用于表示上传文件的字段和文件路径，赞不支持一个字段名上传多个文件

```
"local_file_data":{"image":"head.jpg","file":"mm.docx"}
```

to\_timestamp:用于标识需要转化为时间戳的字段

```
 "to_timestamp":["start_date","end_date"]
```



