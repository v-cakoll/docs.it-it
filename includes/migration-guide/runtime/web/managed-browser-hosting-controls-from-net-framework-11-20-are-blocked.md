### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>I controlli di hosting di browser gestiti da .NET Framework 1.1 e 2.0 sono bloccati

|   |   |
|---|---|
|Dettagli|L'hosting di questi controlli è bloccato in Internet Explorer.|
|Suggerimento|Internet Explorer non riuscirà ad avviare un'applicazione che usa controlli di hosting di browser gestiti. È possibile ripristinare il comportamento precedente impostando il valore EnableIEHosting della sottochiave del Registro di sistema <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> su <code>1</code> per i sistemi x86 e i processi a 32 bit nei sistemi x64 e impostando il valore <code>EnableIEHosting</code> della sottochiave del Registro di sistema <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> su <code>1</code> per i processi a 64 bit nei sistemi x64.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|

