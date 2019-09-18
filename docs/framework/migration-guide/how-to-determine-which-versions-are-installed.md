---
title: 'Procedura: Determinare le versioni di .NET Framework installate'
ms.date: 04/18/2019
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
ms.openlocfilehash: 0df5a5be2997958faa43ee67ae64fc37e1998414
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051598"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Procedura: Determinare le versioni di .NET Framework installate

Gli utenti possono [installare](https://docs.microsoft.com/dotnet/framework/install) ed eseguire nel computer più versioni di .NET Framework. Quando si sviluppa o si distribuisce l'app, potrebbe essere necessario conoscere quali versioni di .NET Framework sono installate nel computer dell'utente.

.NET Framework è costituito da due componenti principali, le cui versioni sono definite separatamente:

- Un set di assembly, ovvero raccolte di tipi e risorse che forniscono la funzionalità per le app. .NET Framework e gli assembly condividono lo stesso numero di versione.

- Common Language Runtime (CLR), che gestisce ed esegue il codice dell'app e che viene identificato dal relativo numero di versione (vedere [Versioni e dipendenze](versions-and-dependencies.md)).

> [!NOTE]
> Ogni nuova versione di .NET Framework conserva funzionalità dalle versioni precedenti e ne aggiunge nuove. È possibile caricare più versioni di .NET Framework in un singolo computer contemporaneamente, il che significa che si può installare .NET Framework senza dover disinstallare le versioni precedenti. In generale, non è necessario disinstallare alcuna versione precedente di .NET Framework, perché un'applicazione in uso potrebbe dipendere da una versione specifica e smettere di funzionare se quella versione viene rimossa.
>
> Esiste una differenza tra la versione di .NET Framework e la versione di CLR:
>
> - La versione di .NET Framework è basata sul set di assembly che costituiscono la libreria di classi .NET Framework. Ad esempio, le versioni di .NET Framework includono 4.5, 4.6.1 e 4.7.2.
>- La versione di CLR è basata sul runtime in cui vengono eseguite le applicazioni .NET Framework. In genere una singola versione di CLR supporta più versioni di .NET Framework. La versione di CLR 4.0.30319.*xxxxx*, ad esempio, supporta le versioni di .NET Framework da 4 a 4.5.2, in cui *xxxxx* è inferiore a 42000, e la versione di CLR 4.0.30319.42000 supporta le versioni di .NET Framework a partire da .NET Framework 4.6.
>
> Per altre informazioni sulle versioni, vedere [Versioni e dipendenze di .NET Framework](versions-and-dependencies.md).

Per ottenere un elenco delle versioni di .NET Framework installate in un computer, accedere al Registro di sistema. È possibile usare l'editor del Registro di sistema per visualizzare il Registro di sistema o eseguire una query tramite codice:

- Trovare le versioni di .NET Framework più recenti (4.5 e successive):
  - [Usare l'editor del Registro di sistema per trovare le versioni di .NET Framework](#net_b)
  - [Eseguire una query tramite codice nel Registro di sistema per trovare le versioni di .NET Framework](#net_d)
  - [Eseguire una query tramite PowerShell nel Registro di sistema per trovare le versioni di .NET Framework](#ps_a)
- Trovare le versioni di .NET Framework precedenti (1 - 4):
  - [Usare l'editor del Registro di sistema per trovare le versioni di .NET Framework](#net_a)
  - [Eseguire una query tramite codice nel Registro di sistema per trovare le versioni di .NET Framework](#net_c)

Per ottenere un elenco delle versioni di CLR installate in un computer, usare uno strumento o codice:

- [Usare lo strumento Clrver](#clr_a)
- [Eseguire una query tramite codice nella classe Environment](#clr_b)

Per informazioni sul rilevamento degli aggiornamenti installati per ogni versione di .NET Framework, vedere [Procedura: Determinare gli aggiornamenti di .NET Framework installati](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="find-newer-net-framework-versions-45-and-later"></a>Trovare le versioni di .NET Framework più recenti (4.5 e successive)

<a name="net_b"></a>

### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>Trovare le versioni di .NET Framework 4.5 e successive del Registro di sistema

1. Dal menu **Start** scegliere **Esegui**, immettere *regedit* e quindi selezionare **OK**.

     Per eseguire regedit, è necessario avere le credenziali amministrative.

2. Nell'Editor del Registro di sistema aprire la seguente sottochiave: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**. Se la sottochiave **Full** non è presente, .NET Framework 4.5 o versioni successive non è installato.

    > [!NOTE]
    > La cartella **NET Framework Setup** nel Registro di sistema *non* inizia con un punto.

3. Verificare la presenza di una voce DWORD denominata **Release**. Se esiste, .NET Framework 4.5 o versioni successive è installato. Il valore è una chiave di rilascio che corrisponde a una particolare versione di .NET Framework. Nella figura seguente, ad esempio, il valore della voce **Release** è *378389*, ovvero la chiave di rilascio per .NET Framework 4.5.

     ![Voce del Registro di sistema per .NET Framework 4.5](./media/clr-installdir.png "Voce del Registro di sistema per .NET Framework 4.5")

La tabella seguente elenca il valore della voce DWORD **Release** nei singoli sistemi operativi per .NET Framework 4.5 e versioni successive.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|Versione di .NET Framework|Valore DWORD di Release|
|--------------------------------|-------------|
|.NET Framework 4.5|Tutti i sistemi operativi Windows: 378389|
|.NET Framework 4.5.1|In Windows 8.1 e Windows Server 2012 R2: 378675<br />In tutti gli altri sistemi operativi Windows: 378758|
|.NET Framework 4.5.2|Tutti i sistemi operativi Windows: 379893|
|.NET Framework 4.6|In Windows 10: 393295<br />In tutti gli altri sistemi operativi Windows: 393297|
|.NET Framework 4.6.1|Nei sistemi Windows 10 con aggiornamento di novembre: 394254<br />In tutti gli altri sistemi operativi Windows (incluso Windows 10): 394271|
|.NET Framework 4.6.2|Nell'Aggiornamento dell'anniversario di Windows 10 e in Windows Server 2016: 394802<br />In tutti gli altri sistemi operativi Windows (inclusi altri sistemi operativi Windows 10): 394806|
|.NET Framework 4.7|In Windows 10 Creators Update: 460798<br />In tutti gli altri sistemi operativi Windows (inclusi altri sistemi operativi Windows 10): 460805|
|.NET Framework 4.7.1|In Windows 10 Fall Creators Update e Windows Server versione 1709: 461308<br/>In tutti gli altri sistemi operativi Windows (inclusi altri sistemi operativi Windows 10): 461310|
|.NET Framework 4.7.2|In Windows 10 aggiornamento di aprile 2018 e Windows Server versione 1803: 461808<br/>In tutti i sistemi operativi diversi dall'Aggiornamento di Windows 10 (aprile 2018) e da Windows Server, versione 1803: 461814|
|.NET Framework 4.8|Aggiornamento di Windows 10 di maggio 2019: 528040<br/>In tutti gli altri sistemi operativi Windows (inclusi altri sistemi operativi Windows 10): 528049|

È possibile usare questi valori come indicato di seguito:

- Per determinare se una versione specifica di .NET Framework è installata in una particolare versione del sistema operativo Windows, verificare se il valore della voce DWORD **Release** è *uguale al* valore elencato nella tabella. Ad esempio, per determinare se .NET Framework 4.6 è presente in un sistema Windows 10, verificare se è presente un valore di **Release** *uguale a* 393295.

- Per determinare se è presente una versione minima di .NET Framework, usare il valore più piccolo di DWORD **RELEASE** per tale versione. Se ad esempio l'applicazione viene eseguita in .NET Framework 4.6 o versione successiva, verificare se è presente un valore della voce DWORD **RELEASE** *maggiore o uguale a* 393295. Per una tabella che elenca solo il valore minimo della voce DWORD **RELEASE** per ogni versione di .NET Framework, vedere [Valori minimi della voce DWORD Release per .NET Framework 4.5 e versioni successive](minimum-release-dword.md).

- Per eseguire questo test per più versioni, iniziare verificando se è presente un valore *maggiore o uguale al* valore più piccolo di DWORD per la versione più recente di .NET Framework e quindi confrontare tale valore con il valore più piccolo di DWORD per ogni versione meno recente. Se ad esempio l'applicazione richiede .NET Framework 4.7 o versione successiva e si vuole determinare quale versione di .NET Framework è presente, iniziare verificando se è presente un valore della voce DWORD **RELEASE** *maggiore o uguale a* 461808 (il valore più piccolo di DWORD per .NET Framework 4.7.2). Confrontare quindi il valore della voce DWORD **RELEASE** con il valore più piccolo per ogni versione successiva di .NET Framework. Per una tabella che elenca solo il valore minimo della voce DWORD **RELEASE** per ogni versione di .NET Framework, vedere [Valori minimi della voce DWORD Release per .NET Framework 4.5 e versioni successive](minimum-release-dword.md).

<a name="net_d"></a>

### <a name="find-net-framework-versions-45-and-later-with-code"></a>Trovare le versioni di .NET Framework 4.5 e successive tramite codice

1. Usare i metodi <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> e <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> per accedere alla sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** nel Registro di sistema di Windows.

    L'esistenza della voce DWORD **Release** nella sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** indica che .NET Framework 4.5 o versioni successive è installato nel computer.

2. Verificare il valore della voce **Release** per determinare la versione installata. Affinché sia compatibile con la versione attualmente installata, è possibile cercare un valore maggiore o uguale ai valori elencati nella [tabella delle versioni di .NET Framework](#version_table).

L'esempio seguente illustra come verificare il valore della voce **Release** nel Registro di sistema per determinare quale versione di .NET Framework 4.5 e versioni successive è installata:

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

Questo esempio segue la procedura consigliata per il controllo della versione:

- Verifica se il valore della voce **Release** è *maggiore o uguale* al valore delle parole chiave Release note.

- Controlla in ordine dalla versione più recente a quella meno recente.

<a name="ps_a"></a>

### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>Verificare la presenza di una versione minima richiesta di .NET Framework (4.5 e versioni successive) con PowerShell

- Usare i comandi PowerShell per verificare il valore della voce **Release** della sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.

Gli esempi seguenti illustrano come verificare il valore della voce **Release** per determinare se .NET Framework 4.6.2 o versioni successive è installato. Questo codice restituisce `True` se è installato e `False` in caso contrario.

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 }
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

Per cercare una versione minima richiesta di .NET Framework diversa, sostituire *394802* in questi esempi con un valore **Release** della [tabella delle versioni di .NET Framework](#version_table).

## <a name="find-older-net-framework-versions-182114"></a>Trovare le versioni di .NET Framework precedenti (1 - 4)

<a name="net_a"></a>

### <a name="find-net-framework-versions-182114-in-the-registry"></a>Trovare le versioni di .NET Framework da 1 a 4 nel Registro di sistema

1. Dal menu **Start** scegliere **Esegui**, immettere *regedit* e quindi selezionare **OK**.

    Per eseguire regedit, è necessario avere le credenziali amministrative.

2. Nell'Editor del Registro di sistema aprire la seguente sottochiave: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:

    - Per le versioni di .NET Framework da 1.1 a 3.5, ogni versione installata è elencata come sottochiave nella sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**. Ad esempio, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**. Il numero di versione è archiviato come valore nella voce **Version** della sottochiave della versione.

    - Per .NET Framework 4, la voce **Version** si trova nella sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, nella sottochiave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** o in entrambe le sottochiavi.

    > [!NOTE]
    > La cartella **NET Framework Setup** nel Registro di sistema non inizia con un punto.

    La figura seguente illustra la sottochiave e la relativa voce **Version** per .NET Framework 3.5.

    ![Voce del Registro di sistema per .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET framework 3.5 e versioni precedenti")

<a name="net_c"></a>

### <a name="find-net-framework-versions-182114-with-code"></a>Trovare le versioni di .NET Framework da 1 a 4 tramite codice

- Usare la classe <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> per accedere alla sottochiave **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** nel Registro di sistema di Windows.

L'esempio seguente illustra come trovare le versioni .NET Framework da 1 a 4 installate:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a>Trovare le versioni di CLR

<a name="clr_a"></a>

### <a name="find-the-current-clr-version-with-clrverexe"></a>Trovare la versione corrente di CLR con Clrver.exe

Usare lo [strumento della versione CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) per determinare le versioni di CLR installate in un computer:

- Da un [Prompt dei comandi per gli sviluppatori per Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) immettere `clrver`.

    Esempio di output:

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="find-the-current-clr-version-with-the-environment-class"></a>Trovare la versione corrente di CLR con la classe Environment

> [!IMPORTANT]
> Per .NET Framework 4.5 e versioni successive, non usare la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per rilevare la versione di CLR. Eseguire invece una query nel Registro di sistema come descritto in [Trovare le versioni di .NET Framework 4.5 e successive tramite codice](#net_d).

1. Eseguire la query per la proprietà <xref:System.Environment.Version?displayProperty=nameWithType> per recuperare un oggetto <xref:System.Version>.

    L'oggetto `System.Version` identifica la versione del runtime che esegue attualmente il codice. Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere state installate nel computer.

    Per le versioni 4, 4.5, 4.5.1 e 4.5.2 di .NET Framework, la rappresentazione stringa dell'oggetto <xref:System.Version> restituito ha il formato 4.0.30319.*xxxxx*, dove *xxxxx* è inferiore a 42000. Per .NET Framework 4.6 e versioni successive, ha il formato 4.0.30319.42000.

2. Dopo aver ottenuto l'oggetto `Version`, eseguire una query come indicato di seguito:

   - Per l'identificatore della versione principale (ad esempio, *4* per la versione 4.0), usare la proprietà <xref:System.Version.Major%2A?displayProperty=nameWithType>.

   - Per l'identificatore della versione secondaria (ad esempio, *0* per la versione 4.0), usare la proprietà <xref:System.Version.Minor%2A?displayProperty=nameWithType>.

   - Per l'intera stringa di versione (ad esempio, *4.0.30319.18010*), usare il metodo <xref:System.Version.ToString%2A?displayProperty=nameWithType>. Questo metodo restituisce un valore singolo che riflette la versione del runtime che esegue il codice. Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere installate nel computer.

L'esempio seguente usa la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per recuperare le informazioni sulla versione di CLR:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Vedere anche

- [Procedura: Determinare gli aggiornamenti di .NET Framework installati](how-to-determine-which-net-framework-updates-are-installed.md)
- [Installare .NET Framework per sviluppatori](../install/guide-for-developers.md)
- [Versioni e dipendenze di .NET Framework](versions-and-dependencies.md)
