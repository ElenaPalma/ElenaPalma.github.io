# Solucionar problemas de instalación de Docker Desktop

Este problema lo tuve aunque mi computadora sí tiene virtualización habilitada y se seguía presentando aún después de haber intentado la instalación varias veces. 
> ❗ Verificar individualmente cada paso abriendo Docker para ver si se resuelve el problema. ❗

## Índice
- [Error](#error)
- [Verificar Virtual Machine y Windows Subsystem for Linux](#verificar-virtual-machine-y-windows-subsystem-for-linux)
- [Verificar compatibilidad con Virtualization](#verificar-compatibilidad-con-virtualization)
- [Reinstalar WSL](#reinstalar-wsl)
- [Fin](#fin)
- [Paginas de referencias](#paginas-de-referencias)


## Error  
![image](https://github.com/user-attachments/assets/19fcfc58-3b1e-44e3-8588-6e8821fd06be)

An unexpected error ocurred while executing a WSL command.
Either shutd own WSL down with wsl --shutdown, and/or reboot your machine. You can also try reinstalling WSL and/or Docker Desktop. If the issue persists, collect diagnostics and submit and issue.  
``
deploying WSL2 distributions
ensuring main distro is deployed: deploying "docker-desktop": importing WSL distro "WSL2 is not supported with your current machine configuration.\r\nPlease enable the \"Virtual Machine Platform\" optional component and ensure virtualization is enabled in the BIOS.
Enable "Virtual Machine Platform" by running: wsl.exe --install --no-distribution
For information please visit https://aka.ms/enablevirtualization
Error code: Wsl/Service/RegisterDistro/CreateVm/HCS/HCS_E_HYPERV_NOT_INSTALLED
: exit status 0xffffffff
checking if isocache exists: CreateFile \\wsl$\docker-desktop-data\isocache\: The network name cannot be found.
``

## Verificar Virtual Machine y Windows Subsystem for Linux

1. Abrir panel de control
2. Abrir Programas y características
3. En el panel izquierdo, buscar 'Habilitar y deshabilitar características de Windows'
4. Asegurarse de que Virtual Machine Platform y Windows Subsystem for Linux estén habilitados
5. Reiniciar la computadora después de activarlos
6. Intentar abrir docker de nuevo

![image](https://github.com/user-attachments/assets/d4d8ef92-39f7-4b2e-a8ac-6c352e050957)

## Verificar compatibilidad con Virtualization

En algunas computadoras, la virtualización se activa directamente entrando al Bios, en mi caso (una Acer Aspire E5-575G) ni si quiera era una opción, pero pude verificar que estaba activo entrando al Administrador de tareas.
Si no esta activo, verifica si tu computadora es compatible y de qué manera se puede habilitar, ya que cada caso es diferente. 

![image](https://github.com/user-attachments/assets/1206a43b-1f16-49e0-b9ba-51e91a7d2be7)

En el menú de Inicio, abrir System information o información del sistema, se puede abrir buscando "msinfo".
En este panel puede encontrar si Virtualization-based security y Hyper-V están activos. 
![image](https://github.com/user-attachments/assets/f5287080-9996-41f5-b124-08bf33ad08da)

## Reinstalar WSL

1. Abrir Windows Powershell como administrador
   
```bash
wsl.exe --install --no-distribution
```
2.	Seleccionar version 2 de wsl como el default en powershell como administrador y reiniciar el equipo

```bash
wsl --set-default-version 2
```

3.	Actualizar wsl en powershell como administrador y reiniciar

```bash
wsl --update
```

4. Nuevamente, abrir powershell como administrador y verificar hypervisor

```bash
bcdedit /enum | findstr -i hypervisorlaunchtype
```

Si devuelve: 
  ``hypervisorlaunchtype Off``
  
Hypervisor no esta activado, para ejecutar lo siguiente y reiniciar el equipo 

```bash
bcdedit /set hypervisorlaunchtype Auto
```

![image](https://github.com/user-attachments/assets/464ee0b3-3190-4700-8648-55e93e95e7b3)


## Fin 
![image](https://github.com/user-attachments/assets/4af8f27e-a823-414e-aa47-1b9b8c05f853)

## Paginas de referencias
*[Stack overflow](https://stackoverflow.com/questions/78621119/docker-desktop-windows-11-unexpected-wsl-error)*  
*[Codingserverfirewall](https://www.configserverfirewall.com/windows-10/wsl-version/)*
