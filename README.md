# VEH-bypass
hack
```C
 void VEH_Bypass(){
	 HMODULE mod = GetModuleHandleA("ntdll.dll");
	 if (mod){
		 DWORD old;
		 DWORD KIException = cast(DWORD, GetProcAddress(mod, "KiUserExceptionDispatcher"));
		 VirtualProtect((LPVOID)KIException, 1, PAGE_EXECUTE_READWRITE, &old);
		 for (int i = 0; i < 24; i++){
			 *(char*)(KIException + i) = 0x90;
		 }
		 VirtualProtect((LPVOID)KIException, 1, old, &old);
	 }
 }
 ```
