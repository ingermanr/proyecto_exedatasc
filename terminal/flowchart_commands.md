```mermaid
flowchart TD
    Start("fa:fa-rocket Terminal Mastery")
    
    %% Setup y comandos básicos
    Setup("fa:fa-tools 🛠️ Comandos Básicos")
    S1["fa:fa-folder Navegación<br>• cd, pwd, ls<br>• dir, Get-Location"]
    S2["fa:fa-file Archivos<br>• touch, cp, mv<br>• New-Item, Copy-Item"]
    S3["fa:fa-search Búsqueda<br>• find, locate<br>• Get-ChildItem"]
    S4["fa:fa-eye Visualización<br>• cat, less, more<br>• Get-Content"]

    %% Procesamiento de texto
    Text("fa:fa-file-alt 📝 Procesamiento Texto")
    T1["fa:fa-filter Filtrado<br>• grep, awk, sed<br>• Select-String"]
    T2["fa:fa-sort Ordenamiento<br>• sort, uniq<br>• Sort-Object"]
    T3["fa:fa-random Transformación<br>• tr, cut<br>• ForEach-Object"]

    %% Sistema y procesos
    System("fa:fa-microchip ⚙️ Sistema")
    Sys1["fa:fa-tasks Procesos<br>• ps, top, kill<br>• Get-Process"]
    Sys2["fa:fa-hdd Recursos<br>• df, du, free<br>• Get-PSDrive"]
    Sys3["fa:fa-network-wired Red<br>• netstat, curl<br>• Test-Connection"]

    %% Automatización
    Auto("fa:fa-robot 🤖 Automatización")
    A1["fa:fa-code Scripts<br>• bash, sh<br>• .ps1 scripts"]
    A2["fa:fa-clock Tareas<br>• cron, at<br>• Task Scheduler"]
    A3["fa:fa-terminal Pipeline<br>• pipes |<br>• cmdlets"]

    %% Herramientas DS
    DataSci("fa:fa-brain 📊 Data Science")
    D1["fa:fa-table Datos<br>• csvkit, mlr<br>• Import-Csv"]
    D2["fa:fa-code-branch Git<br>• git commands<br>• mismo en ambos"]
    D3["fa:fa-docker Docker<br>• docker cmds<br>• mismo en ambos"]

    %% Conexiones principales
    Start --> Setup
    Start --> Text
    Start --> System
    Start --> Auto
    Start --> DataSci

    %% Conexiones Setup
    Setup --> S1 & S2 & S3 & S4

    %% Conexiones Texto
    Text --> T1 & T2 & T3

    %% Conexiones Sistema
    System --> Sys1 & Sys2 & Sys3

    %% Conexiones Auto
    Auto --> A1 & A2 & A3

    %% Conexiones DataSci
    DataSci --> D1 & D2 & D3

    %% Estilos
    style Start fill:#2962FF,stroke:#2962FF,color:#FFF
    style Setup fill:#00BFA5,stroke:#00BFA5,color:#FFF
    style Text fill:#FFB300,stroke:#FFB300,color:#FFF
    style System fill:#7C4DFF,stroke:#7C4DFF,color:#FFF
    style Auto fill:#F50057,stroke:#F50057,color:#FFF
    style DataSci fill:#00C853,stroke:#00C853,color:#FFF

    %% Estilos de subnodos
    classDef subnode fill:#FFF,stroke:#333,stroke-width:2px
    class S1,S2,S3,S4,T1,T2,T3,Sys1,Sys2,Sys3,A1,A2,A3,D1,D2,D3 subnode