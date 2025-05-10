# VEH

```C
 void VEH_Bypass(){
	 HMODULE mod = GetModuleHandleA("ntdll.dll");
		 DWORD old;
		 DWORD KIException = cast(DWORD, GetProcAddress(mod, "KiUserExceptionDispatcher"));

 }
 ```
