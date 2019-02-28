---
title: 'Procedura: Determinare le versioni di .NET Framework installate'
ms.date: 02/20/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584174"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Procedura: Determinare le versioni di .NET Framework installate

Gli utenti possono installare ed eseguire nel computer più versioni di .NET Framework. Quando si sviluppa o si distribuisce l'app, potrebbe essere necessario conoscere quali versioni di .NET Framework sono installate nel computer dell'utente. Si noti che .NET Framework è costituito da due componenti principali, le cui versioni sono definite separatamente:  
  
- Un set di assembly, ovvero raccolte di tipi e risorse che forniscono la funzionalità per le app. .NET Framework e gli assembly condividono lo stesso numero di versione.  
  
- Common Language Runtime (CLR), che gestisce ed esegue il codice dell'app e che viene identificato dal relativo numero di versione (vedere [Versioni e dipendenze](~/docs/framework/migration-guide/versions-and-dependencies.md)).  
  
Per ottenere un elenco accurato delle versioni di .NET Framework installate in un computer, è possibile visualizzare il Registro di sistema o eseguire query sul Registro di sistema nel codice:  
  
 [Trovare le versioni di .NET Framework 1-4 nel Registro di sistema](#net_a)  
 [Trovare le versioni di .NET Framework 4.5 e successive del Registro di sistema](#net_b)  
 [Uso del codice per eseguire query sul Registro di sistema (versioni 1-4)](#net_c)  
 [Uso del codice per eseguire query sul Registro di sistema (versione 4.5 e successive)](#net_d)  
 [Uso di PowerShell per eseguire query sul Registro di sistema (versione 4.5 e successive)](#ps_a)  

 Per trovare la versione di CLR, è possibile usare uno strumento o il codice:  
  
 [Uso dello strumento Clrver](#clr_a)  
 [Uso del codice per eseguire query sulla classe System.Environment](#clr_b)  

> [!NOTE]
> Esiste una differenza tra la versione di .NET Framework e la versione di Common Language Runtime (CLR). Le versioni di .NET Framework sono basate sul set di assembly che costituiscono la libreria di classi .NET Framework. Ad esempio, le versioni di .NET Framework includono 4.5, 4.6.1 e 4.7.2. Le versioni di CLR sono basate sul runtime in cui vengono eseguite le applicazioni di .NET Framework e una singola versione di CLR supporta in genere più versioni di .NET Framework. La versione di CLR 4.30319.*xxxxx* supporta le versioni di .NET Framework da 4 a 4.5.2. La versione di CLR 4.30319.42000 supporta le versioni di .NET Framework a partire da .NET Framework 4.6. Per altre informazioni, vedere la proprietà <xref:System.Environment.Version?displayProperty=nameWithType>.

 Per informazioni sul rilevamento degli aggiornamenti installati per ogni versione di .NET Framework, vedere [Procedura: Determinare gli aggiornamenti di .NET Framework installati](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md). Per informazioni sull'installazione di .NET Framework, vedere [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Installare .NET Framework per sviluppatori).  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a>Trovare le versioni di .NET Framework 1-4 nel Registro di sistema 
  
1.  Scegliere **Esegui** dal menu **Start**.  
  
2.  Nella casella **Apri** immettere **regedit.exe**.  
  
     Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.  
  
3.  Nell'Editor del Registro di sistema aprire la seguente sottochiave:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     Per le versioni di .NET Framework da 1.1 a 3.5, le versioni installate sono elencate come sottochiavi della sottochiave `NDP`. Il numero di versione è archiviato nella voce **Version** della sottochiave della versione. 
     
     Per .NET Framework 4, la voce **Version** è nella sottochiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client`, nella sottochiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` o in entrambe.

    > [!NOTE]
    > La cartella "NET Framework Setup" nel Registro di sistema non inizia con un punto.

    La figura seguente mostra la sottochiave per .NET Framework 3.5 con la relativa voce **Version**.

     ![Voce del Registro di sistema per .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET framework 4 e versioni precedenti")

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>Trovare le versioni di .NET Framework 4.5 e successive del Registro di sistema

1. Scegliere **Esegui** dal menu **Start**.

2. Nella casella **Apri** immettere **regedit.exe**.

     Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.

3. Nell'Editor del Registro di sistema aprire la seguente sottochiave:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     Si noti che il percorso della sottochiave `Full` include la sottochiave `Net Framework` e non `.NET Framework`.

    > [!NOTE]
    > Se la sottochiave `Full` non è presente, .NET Framework 4.5 o versione successiva non è installato.

     Verificare la presenza di un valore DWORD denominato `Release`. L'esistenza del valore DWORD `Release` indica che nel computer è stato installato .NET Framework 4.5 o versione successiva. Il valore è una chiave di rilascio che corrisponde a una particolare versione di .NET Framework. Nella figura seguente, ad esempio, il valore DWORD `Release` è 378389, ovvero la chiave di rilascio per .NET Framework 4.5. 

     ![Voce del Registro di sistema per .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")

La tabella seguente elenca il valore minimo DWORD `Release` per ogni versione di .NET Framework. È possibile usare questi valori come indicato di seguito:

- Per determinare se è presente una versione minima di .NET Framework, verificare se il valore DWORD `Release` trovato nel Registro di sistema è *maggiore o uguale* al valore elencato nella tabella. Ad esempio, se l'applicazione richiede .NET Framework 4.7 o versioni successive, eseguire un test per il valore minimo della chiave di rilascio 460798.

- Per eseguire il test per più versioni, iniziare con la versione più recente di .NET Framework e quindi ripetere il test per ogni versione precedente successiva.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|Versione di .NET Framework|Valore DWORD di Release|
|--------------------------------|-------------|
|.NET Framework 4.5|378389|
|.NET Framework 4.5.1|378675|
|.NET Framework 4.5.2|379893|
|.NET Framework 4.6|393295|
|.NET Framework 4.6.1|394254|
|.NET Framework 4.6.2|394802|
|.NET Framework 4.7|460798|
|.NET Framework 4.7.1|461308|
|.NET Framework 4.7.2|461808|

Per una tabella completa delle chiavi di rilascio per .NET Framework per versioni specifiche del sistema operativo Windows, vedere [Chiavi di rilascio di .NET Framework e versioni del sistema operativo Windows](release-keys-and-os-versions.md).

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a>Trovare le versioni di .NET Framework 1-4 tramite codice

- Usare la classe <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> per accedere alla sottochiave `Software\Microsoft\NET Framework Setup\NDP\` nel ramo `HKEY_LOCAL_MACHINE` nel Registro di sistema Windows.

     Nel codice seguente viene illustrato un esempio di questa query.

    > [!NOTE]
    > Questo codice non mostra come rilevare .NET Framework 4.5 o versione successiva. Controllare il valore DWORD `Release` per rilevare tali versioni, come descritto nella sezione precedente. Per il codice che rileva .NET Framework 4.5 o versioni successive, vedere la sezione successiva in questo articolo.

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a>Trovare le versioni di .NET Framework 4.5 e successive tramite codice

1. L'esistenza del valore DWORD `Release` nella chiave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` indica che nel computer è stato installato .NET Framework 4.5 o versione successiva. Il valore di questa parola chiave indica la versione installata. Per controllare questa parola chiave, usare i metodi <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> e <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> per accedere alla sottochiave nel Registro di sistema di Windows.

2. Verificare il valore della parola chiave `Release` per determinare la versione installata. Per essere compatibili con le versioni successive, è possibile cercare un valore maggiore o uguale di quello elencato nella tabella nella sezione [Trovare le versioni di .NET Framework 4.5 e successive del Registro di sistema](#net_b) sezione.

Nell'esempio seguente viene controllato il valore `Release` nel Registro di sistema per determinare se è installato .NET Framework 4.5 o una versione successiva.

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

Questo esempio segue la procedura consigliata per il controllo della versione:

- Controlla se il valore della voce `Release` è *maggiore o uguale* al valore delle parole chiave Release note.

- Controlla in ordine dalla versione più recente a quella meno recente.

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>Controllare la presenza di una versione minima richiesta di .NET Framework (4.5 e versioni successive) con PowerShell

Nell'esempio seguente viene controllato il valore della parola chiave `Release` per determinare se è installato .NET Framework 4.6.2 o versione successiva (viene restituito `True` in caso di esito positivo e `False` in caso contrario).

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a>Trovare la versione corrente di CLR con Clrver.exe

Usare lo strumento CLR Version (Clrver.exe) per determinare le versioni di Common Language Runtime installate in un computer.

Da un prompt dei comandi per gli sviluppatori per Visual Studio, immettere `clrver`. Questo comando consente di generare un output analogo a quello illustrato di seguito.

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

Per altre informazioni sull'uso di questo strumento, vedere [Clrver.exe (strumento della versione CLR)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a>Trovare la versione corrente di CLR con la classe Environment

È possibile recuperare il valore della proprietà <xref:System.Environment.Version?displayProperty=nameWithType> per recuperare un oggetto <xref:System.Version> che identifica la versione del runtime che esegue attualmente il codice. Questa proprietà restituisce un singolo valore che riflette la versione del runtime che esegue il codice. Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere state installate nel computer. È possibile usare la proprietà <xref:System.Version.Major%2A?displayProperty=nameWithType> per ottenere l'identificatore di versione principale (ad esempio, "4" per la versione 4.0), la proprietà <xref:System.Version.Minor%2A?displayProperty=nameWithType> per ottenere l'identificatore della versione secondaria (ad esempio, "0" per la versione 4.0) oppure il metodo <xref:System.Version.ToString%2A?displayProperty=nameWithType> per ottenere l'intera stringa della versione (ad esempio "4.0.30319.18010", come illustrato nel codice seguente). 

Per le versioni 4, 4.5, 4.5.1 e 4.5.2 di .NET Framework, la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> restituisce un oggetto <xref:System.Version> la cui rappresentazione di stringa ha il formato `4.0.30319.xxxxx`. In .NET Framework 4.6 e versioni successive, ha il formato `4.0.30319.42000`.

> [!IMPORTANT]
> Per .NET Framework 4.5 e versioni successive, non è consigliabile usare la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per rilevare la versione del runtime. Si consiglia invece di eseguire una query sul Registro di sistema, come descritto nella sezione [Per trovare le versioni di .NET Framework eseguendo query sul Registro di sistema nel codice (.NET Framework 4.5 e versioni successive)](#net_d) riportata in precedenza in questo articolo.

Nell'esempio seguente viene usata la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per recuperare le informazioni sulla versione del runtime:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Vedere anche

- [Procedura: Determinare gli aggiornamenti di .NET Framework installati](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [Installare .NET Framework per sviluppatori](../../../docs/framework/install/guide-for-developers.md)
- [Versioni e dipendenze](~/docs/framework/migration-guide/versions-and-dependencies.md)
