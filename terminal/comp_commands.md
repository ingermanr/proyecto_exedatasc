# Comandos Esenciales: Windows (PowerShell) vs Linux

## 1. Navegación y Sistema de Archivos
| Operación | Linux | Windows (PowerShell) |
|-----------|-------|---------------------|
| Directorio actual | pwd | Get-Location (pwd) |
| Listar archivos | ls -la | Get-ChildItem (ls, dir) |
| Cambiar directorio | cd ruta | Set-Location ruta (cd) |
| Crear directorio | mkdir dir | New-Item -Type Directory dir |
| Crear archivo | touch archivo | New-Item archivo |
| Copiar | cp origen destino | Copy-Item origen destino |
| Mover/Renombrar | mv origen destino | Move-Item origen destino |
| Eliminar | rm archivo | Remove-Item archivo |
| Ver contenido | cat archivo | Get-Content archivo |
| Buscar archivos | find /ruta -name "*.txt" | Get-ChildItem -Path ruta -Filter "*.txt" -Recurse |
| Permisos | chmod 755 archivo | icacls archivo /grant "usuarios:(RX)" |

## 2. Procesamiento de Texto
| Operación | Linux | Windows (PowerShell) |
|-----------|-------|---------------------|
| Buscar texto | grep "patrón" archivo | Select-String -Pattern "patrón" archivo |
| Ordenar | sort archivo | Sort-Object archivo |
| Contar líneas | wc -l archivo | (Get-Content archivo).Length |
| Filtrar columnas | cut -d',' -f1,2 archivo | Import-Csv archivo \| Select-Object Col1,Col2 |
| Reemplazar texto | sed 's/viejo/nuevo/g' | (Get-Content archivo).Replace("viejo","nuevo") |

## 3. Procesos y Sistema
| Operación | Linux | Windows (PowerShell) |
|-----------|-------|---------------------|
| Listar procesos | ps aux | Get-Process |
| Matar proceso | kill PID | Stop-Process -Id PID |
| Uso de disco | df -h | Get-PSDrive |
| Uso de memoria | free -h | Get-Counter '\Memory\*' |
| Info sistema | uname -a | Get-ComputerInfo |
| Monitor procesos | top | Get-Process \| Sort-Object CPU -Descending |

## 4. Networking
| Operación | Linux | Windows (PowerShell) |
|-----------|-------|---------------------|
| Test conexión | ping host | Test-Connection host |
| Estado red | netstat -an | Get-NetTCPConnection |
| Descargar | wget url | Invoke-WebRequest url |
| DNS lookup | nslookup dominio | Resolve-DnsName dominio |

## 5. Data Science Específico
| Operación | Linux | Windows (PowerShell) |
|-----------|-------|---------------------|
| CSV parsing | csvkit | Import-Csv |
| JSON parsing | jq | ConvertFrom-Json |
| Compresión | tar -czf archivo.tar.gz dir | Compress-Archive -Path dir -DestinationPath archivo.zip |
| Ambiente Python | source venv/bin/activate | .\venv\Scripts\Activate.ps1 |
| Git status | git status | git status |
| Docker ps | docker ps | docker ps |

## 6. Automatización
| Operación | Linux | Windows (PowerShell) |
|-----------|-------|---------------------|
| Scripts | bash script.sh | .\script.ps1 |
| Tareas programadas | crontab -e | Register-ScheduledTask |
| Variables ambiente | export VAR=valor | $env:VAR = "valor" |
| Pipes | comando1 \| comando2 | comando1 \| comando2 |
| Loops | for i in {1..5}; do echo $i; done | 1..5 \| ForEach-Object { $_ } |