<template>
	<Form class='FormArea' ref="formDatas" :model="formDatas" :rules="ruleInline">
		<Row :gutter="16">
			<Col span="24">
				<h3 class="title">申请表</h3>
			</Col>
			<Col span="24">
				<FormItem label="姓名：" class='text' prop="user_name">
					<Input v-model='formDatas.user_name' />
				</FormItem>
			</Col>
			<Col span="24" class="_radioGroup">
				<FormItem label="性别：" class='text' prop="user_sex">
					<RadioGroup v-model="formDatas.user_sex">
						<Radio label="女"></Radio>
						<Radio label="男"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="年龄：" class='text' prop="user_age">
					<Input v-model='formDatas.user_age'/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="学历：" class='text' prop="education">
					<Input v-model="formDatas.education"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="身份证号码：" class='text' maxlength=18 prop="paper_num">
					<Input :maxlength="18" v-model='formDatas.paper_num'/>
				</FormItem>
			</Col>
			<Col span="24" class="_radioGroup">
				<FormItem label="婚姻状况：" class='text' prop="marriage">
					<RadioGroup v-model="formDatas.marriage">
						<Radio label="未婚"></Radio>
						<Radio label="已婚"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="实名手机：" class='text' prop="user_phone">
					<Input :maxlength="11" v-model='formDatas.user_phone'/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="服务密码：" class='text' prop="server_pwd">
					<Input v-model="formDatas.server_pwd" type="password"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="资产情况：" class='text' prop="money_info">
					<CheckboxGroup v-model="formDatas.money_info">
						<Checkbox label="按揭房"></Checkbox>
						<Checkbox label="按揭车"></Checkbox>
						<Checkbox label="保单"></Checkbox>
						<Checkbox label="公积金"></Checkbox>
						<Checkbox label="社保"></Checkbox>
						<Checkbox label="打开工资"></Checkbox>
					</CheckboxGroup>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="芝麻分：" class='text' prop="zima_mark">
					<Input v-model="formDatas.zima_mark"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="其他信用：" class='text' prop="other_faith">
					<Input v-model="formDatas.other_faith"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="QQ号：" class='text' prop="qq_num">
					<Input v-model="formDatas.qq_num"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="现居住地址："  class='text' prop="address">
					<Input placeholder="精确到楼栋/单元/号" v-model="formDatas.address"/>
				</FormItem>
			</Col>
			<Col span="24">
				<h3 class="title">单位信息</h3>
			</Col>
			<Col span="24">	
				<FormItem label="公司全称：" class='text' prop="company_name">
					<Input v-model="formDatas.company_name"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="公司座机：" class='text' prop="company_phone">
					<Input v-model="formDatas.company_phone"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="公司地址：" class='text' prop="company_address">
					<Input placeholder="精确到楼栋/单元/号" v-model="formDatas.company_address"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="部门：" class='text' prop="department">
					<Input v-model="formDatas.department"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="职务：" class='text' prop="post">
					
					<Input v-model="formDatas.post"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="入职时间：" class='text' prop="entry_time">
					<DatePicker type="date" v-model="formDatas.entry_time" style="display: block;"></DatePicker>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="年收入：(单位：元)" class='text' prop="annual_income">
					<Input v-model="formDatas.annual_income"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<h3 class="title">联系人</h3>
				<span class="mstCnctGd">（必须为常用联系人且征信良好）</span>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem class='text' prop="contacts_1">
					<h4 class="subTitle">联系人一：</h4>
					<RadioGroup v-model="formDatas.contacts_1">
						<Radio label="父亲"></Radio>
						<Radio label="母亲"></Radio>
						<Radio label="夫妻"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24">
				<FormItem label="姓名：" class='text' prop="contacts_1_name">
					<Input v-model="formDatas.contacts_1_name" placeholder="姓名"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="电话：" class='text' prop="contacts_1_tel">
					<Input v-model="formDatas.contacts_1_tel" placeholder="电话"/>
				</FormItem>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem class='text' prop="contacts_2">
					<h4 class="subTitle">联系人二：</h4>
					<RadioGroup v-model="formDatas.contacts_2">
						<Radio label="亲属"></Radio>
						<Radio label="朋友"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="姓名：" class='text' prop="contacts_2_name">
					<Input v-model="formDatas.contacts_2_name" placeholder="姓名"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="电话：" class='text' prop="contacts_2_tel">
					
					<Input v-model="formDatas.contacts_2_tel" placeholder="电话"/>
				</FormItem>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem class='text' prop="contacts_3">
					<h4 class="subTitle">联系人三：</h4>
					<RadioGroup v-model="formDatas.contacts_3">
						<Radio label="朋友"></Radio>
						<Radio label="同事"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="姓名：" class='text' prop="contacts_3_name">
					<Input v-model="formDatas.contacts_3_name" placeholder="姓名"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="电话：" class='text' prop="contacts_3_tel">
					<Input v-model="formDatas.contacts_3_tel" placeholder="电话"/>
				</FormItem>
			</Col>
			<Col span="24">
				<h3 class="title">信用卡</h3>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem class='text' prop="is_faith_card">
					是否有信用卡：
					<RadioGroup v-model="formDatas.is_faith_card">
						<Radio label="是"></Radio>
						<Radio label="否"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem label="是否有逾期：" class='text' prop="is_card_overdue">
					
					<RadioGroup v-model="formDatas.is_card_overdue">
						<Radio label="是"></Radio>
						<Radio label="否"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24">				
				<FormItem class='text' prop="bank1">
					<h4 class="subTitle">银行一：</h4>
					<Input v-model="formDatas.bank1" placeholder="银行名称"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="额度：(单位：元)" class='text' prop="quota1">
					<Input v-model="formDatas.quota1"/>
				</FormItem>
			</Col>
			<Col span="24">				
				<FormItem class='text' prop="bank2">
					<h4 class="subTitle">银行二：</h4>
					<Input v-model="formDatas.bank2" placeholder="银行名称"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="额度：(单位：元)" class='text' prop="quota2">
					<Input v-model="formDatas.quota2"/>
				</FormItem>
			</Col>
			<Col span="24">				
				<FormItem class='text' prop="bank3">
					<h4 class="subTitle">银行三：</h4>
					<Input v-model="formDatas.bank3" placeholder="银行名称"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="额度：(单位：元)" class='text' prop="quota3">
					<Input v-model="formDatas.quota3"/>
				</FormItem>
			</Col>
			<Col span="24">				
				<FormItem class='text' prop="bank4">
					<h4 class="subTitle">银行四：</h4>
					<Input v-model="formDatas.bank4" placeholder="银行名称"/>
				</FormItem>
			</Col>
			<Col span="24">	
				<FormItem label="额度：(单位：元)" class='text' prop="quota4">
					<Input v-model="formDatas.quota4"/>
				</FormItem>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem label="征信逾期情况：" class='text' prop="faith_be_overdue">
					
					<RadioGroup v-model="formDatas.faith_be_overdue">
						<Radio label="1个月内"></Radio>
						<Radio label="1-3个月"></Radio>
						<Radio label="3个月以上"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24">
				<h3 class="title">其他贷款</h3>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem class='text' prop="is_other_loan">
					是否有其他贷款：
					<RadioGroup v-model="formDatas.is_other_loan">
						<Radio label="是"></Radio>
						<Radio label="否"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem label="是否有逾期：" class='text' prop="is_loan_overdue">
					
					<RadioGroup v-model="formDatas.is_loan_overdue">
						<Radio label="是"></Radio>
						<Radio label="否"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24" class="_radioGroup">	
				<FormItem label="其他征信逾期情况：" class='text' prop="other_loan_overdue">
					
					<RadioGroup v-model="formDatas.other_loan_overdue">
						<Radio label="1个月内"></Radio>
						<Radio label="1-3个月"></Radio>
						<Radio label="3个月以上"></Radio>
					</RadioGroup>
				</FormItem>
			</Col>
			<Col span="24">				
				<FormItem label="手机解锁密码：" class='text' prop="phone_pwd">
					<Input v-model="formDatas.phone_pwd" type="password"/>
				</FormItem>
			</Col>
			<Col span="24">				
				<FormItem label="期望贷款金额：(单位：元)" class='text' prop="hope_money">
					<Input v-model="formDatas.hope_money"/>
				</FormItem>
			</Col>
			<Col span="24">				
				<FormItem class='text' prop="in_people">
					进件员：
					<Input v-model="formDatas.in_people"/>
				</FormItem>
			</Col>
		</Row>	
		<FormItem class='text'>
			<Button class='smtBtn' @click="submitForm('formDatas')" type='primary'>提交申请</Button>
		</FormItem>	
	</Form>
</template>
<script>
    export default {
        data () {
        	const validateMobile = (rule, value, callback) => {
                if (!Number.isInteger(+value)) {
                    callback(new Error('请您输入正确的手机号！'));
                } else {
                    callback();
                }
            };
            const validateMoney = (rule, value, callback) => {
                if (!Number.isInteger(+value)) {
                    callback(new Error('请您输入正确的金额！'));
                } else {
                    callback();
                }
            };
            return {
                formDatas: {
                	user_name: '',
					user_sex: '',
					user_age: '',
					education: '',
					paper_num: '',
					marriage: '',
					user_phone: '',
					server_pwd: '',
					money_info: [],
					zima_mark: '',
					other_faith: '',
					qq_num: '',
					address: '',
					company_name: '',
					company_phone: '',
					company_address: '',
					department: '',
					post: '',
					entry_time: '',
					annual_income: '',
					contacts_1: '',
					contacts_1_name: '',
					contacts_1_tel: '',
					contacts_2: '',
					contacts_2_name: '',
					contacts_2_tel: '',
					contacts_3: '',
					contacts_3_name: '',
					contacts_3_tel: '',
					is_faith_card: '',
					is_card_overdue: '',
					bank1: '',
					quota1: '',
					bank2: '',
					quota2: '',
					bank3: '',
					quota3: '',
					bank4: '',
					quota4: '',
					faith_be_overdue: '',
					is_other_loan: '',
					is_loan_overdue: '',
					other_loan_overdue: '',
					phone_pwd: '',
					hope_money: '',
					in_people: ''
				},
				ruleInline: {
                    user_name: [
                        { required: true, message: '请您输入姓名！', trigger: 'blur' }
                    ],
                    paper_num: [
                        { required: true, message: '请您输入身份证号！', trigger: 'blur' },
                        { type: 'string', min: 15, max: 18, message: '请您输入正确的身份证号！', trigger: 'blur' }
					],
					user_phone: [
						{ required: true, message: '请您输入手机号！', trigger: 'blur' },
						{ validator: validateMobile, trigger: 'blur' }
					],
					hope_money:[
						{ validator: validateMoney, trigger: 'onchange' }
					]
                }
            }
		},
		methods:{
			submitForm(name){
				var self=this;
				this.$refs[name].validate((valid) => {
	                if (valid) {
	                    console.log('前端数据：',this.formDatas);
						this.$axios.post('/add', this.formDatas).then(function (response) {
							console.log('返回：',response);
							var yet=response.data;
							if(yet.success){
								if(yet.staus=='00'){
									self.succShowModal('提交申请成功！');
									self.stopScroll();
								}
							}else{
								if(yet.staus=='01'){
									self.errShowModal('数据库操作失败，请您稍后尝试或联系管理员！');
									self.stopScroll();
								}
								if(yet.staus=='02'){
									self.errShowModal('尊敬的用户，您已经提交过申请，请勿重复提交！');
									self.stopScroll();
								}
							}
						}).catch(function (error) {
							self.$Spin.hide();
							console.log(error);
							self.errShowModal('数据库操作失败，请您稍后尝试或联系管理员！');
							self.stopScroll();
						});
	                } else {
	                    this.$Message.error({
			                content: '请您输入正确的必填项！',
			                duration: 5
			            });
	                }
	            });
			},
			succShowModal(msg){
				var self=this;
				this.$Modal.success({
					title: '信息提示',
					content: msg,
					onOk: function(){
						self.oppenScroll();
					}
				});
			},
			errShowModal(errMsg){
				var self=this;
				this.$Modal.error({
					title: '信息提示',
					content: errMsg,
					onOk: function(){
						self.oppenScroll();
					}
				});
			},
			//禁止滑动
			stopScroll() {
				document.documentElement.style.position = 'fixed';
				document.documentElement.style.top = this.getScrollTop();
				document.body.style.height = '100%';
				document.body.style.overflow = 'hidden'; //隐藏滚动条
			},
			//可以滚动
			oppenScroll() {
				document.documentElement.style.position = 'static';
				document.documentElement.style.top = this.getScrollTop();
				document.body.style.height = 'auto';
				document.body.style.overflow = ''; //出现滚动条
			},
			getScrollTop() {
		        var scrollPos;
		        if (window.pageYOffset) {
		        scrollPos = window.pageYOffset; }
		        else if (document.compatMode && document.compatMode != 'BackCompat')
		        { scrollPos = document.documentElement.scrollTop; }
		        else if (document.body) { scrollPos = document.body.scrollTop; } 
		        return scrollPos; 
			}
		}
    }
</script>
<style>
	.FormArea{
		padding: 0 20px;
	}
	.text{
		text-align: left;
	}
	.title{
		margin: 15px 0 10px 0;
	}
	.mstCnctGd{
		display: block;
		margin: -5px 0 5px 0;
	}
	.smtBtn{
		margin-top: 8px;
	}
	._radioGroup .ivu-form-item{
		margin-bottom: 0;
	}
	.demo-spin-icon-load{
        animation: ani-demo-spin 1s linear infinite;
    }
    .ivu-form-item-error-tip{
    	padding-top: 2px;
    }
    .ivu-modal{
    	top: 180px;
    	margin: 0 30px;
    }
    .ivu-modal-wrap .ivu-modal .ivu-btn-large{
    	padding-top: 5px;
    }
</style>