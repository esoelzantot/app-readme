SIGN-UP

##### **_Scenario-1_**

- ###### **first time with new email ->**

1. **_SIGNUP-API_**
   status: 201
   message: "تم إنشاء الحساب بنجاح، يرجى تأكيد كود التحقق"

2. **_VERIFY-API_**
   status: 200
   message: "تم تفعيل الحساب بنجاح"

3. **_COMPLETE-API_**
   status: 200
   message: "تم استكمال الملف الشخصي بنجاح"

4. **_LOGIN-API_**
   status: 200
   message: "تم تسجيل الدخول بنجاح"

##### **_Scenario-2_**

- ###### **signup with existing email->**

1. **_SIGNUP-API_**
   status: 409
   Code: null
   message: "يوجد مستخدم بالفعل بهذا البريد أو الهاتف"

2. **_LOGIN-API_**
   status: 200
   message: "تم تسجيل الدخول بنجاح"

- ###### **signup with existing email without verify->**

1. **_SIGNUP-API_**
   status: 409
   Code: null
   message: "يوجد مستخدم بالفعل بهذا البريد أو الهاتف"

2. **_LOGIN-API_**
   status: 403
   Code: "NOT_VERIFIED",
   message: "من فضلك قم بتفعيل حسابك أولاً"

- ###### **signup with existing email without complete profile->**

1. **_SIGNUP-API_**
   status: 409
   Code: null
   message: "يوجد مستخدم بالفعل بهذا البريد أو الهاتف"

2. **_LOGIN-API_**
   status: 200
   Code: "PROFILE_INCOMPLETE",
   message: "من فضلك قم بتفعيل حسابك أولاً"
   token: "token-value"
