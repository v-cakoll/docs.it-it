---
title: Determinare le versioni di .NET Framework installate
description: Usare code, regedit.exe o PowerShell per rilevare quali versioni di .NET Framework sono installate in un computer eseguendo una query sul Registro di sistema di Windows.
ms.date: 02/03/2020
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: 8469f977c6ed9691c81a2a8354935557b5c27171
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77093831"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Procedura: Determinare le versioni di .NET Framework installate

Gli utenti possono [installare](../install/index.md) ed eseguire più versioni di .NET Framework nei propri computer. Quando si sviluppa o si distribuisce l'app, potrebbe essere necessario conoscere quali versioni di .NET Framework sono installate nel computer dell'utente. Il Registro di sistema contiene un elenco delle versioni di .NET Framework installate in un computer.

.NET Framework è costituito da due componenti principali, le cui versioni sono definite separatamente:

- Un set di assembly, ovvero raccolte di tipi e risorse che forniscono la funzionalità per le app. .NET Framework e gli assembly condividono lo stesso numero di versione. Ad esempio, le versioni di .NET Framework includono 4.5, 4.6.1 e 4.7.2.

- Common Language Runtime (CLR), che gestisce ed esegue il codice dell'app In genere una singola versione di CLR supporta più versioni di .NET Framework. Ad esempio, CLR versione 4.0.30319.For example, CLR version 4.0.30319. *xxxxx* dove *xxxxx* è minore di 42000, supporta .NET Framework versioni da 4 a 4.5.2. La versione CLR maggiore o uguale alla 4.0.30319.42000 supporta le versioni di .NET Framework a partire da .NET Framework 4.6.

Sono disponibili strumenti gestiti dalla community per rilevare le versioni di .NET Framework installate:

- [https://github.com/jmalarcon/DotNetVersions](https://github.com/jmalarcon/DotNetVersions)

  Uno strumento da riga di comando .NET 2.0.

- [https://github.com/EliteLoser/DotNetVersionLister](https://github.com/EliteLoser/DotNetVersionLister)

  Un modulo di PowerShell 2.0.A PowerShell 2.0 module.

Per informazioni sul rilevamento degli aggiornamenti installati per ogni versione di .NET Framework, vedere [Procedura: determinare quali aggiornamenti di .NET Framework sono installati.](how-to-determine-which-net-framework-updates-are-installed.md)

## <a name="detect-net-framework-45-and-later-versions"></a>Rilevare .NET Framework 4.5 e versioni successive

La versione di .NET Framework (4.5 e versioni successive) installata in un computer è elencata nel Registro di sistema in **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**. Se la sottochiave **Full** non è presente, .NET Framework 4.5 o versione successiva non è installato.

> [!NOTE]
> La sottochiave di installazione di **NET Framework** nel percorso del Registro di sistema *non* inizia con un punto.

Il valore **Release** REG_DWORD nel Registro di sistema rappresenta la versione di .NET Framework installata.

<a name="version_table"></a>

| Versione di .NET Framework | Valore del **rilascio** |
| ---------------------- | -------------------------- |
| .NET Framework 4.5     | Tutti i sistemi operativi Windows: 378389 |
| .NET Framework 4.5.1   | In Windows 8.1 e Windows Server 2012 R2: 378675<br />In tutti gli altri sistemi operativi Windows: 378758 |
| .NET Framework 4.5.2   | Tutti i sistemi operativi Windows: 379893 |
| .NET Framework 4.6     | In Windows 10: 393295<br />In tutti gli altri sistemi operativi Windows: 393297 |
| .NET Framework 4.6.1   | Nei sistemi Windows 10 con aggiornamento di novembre: 394254<br />In tutti gli altri sistemi operativi Windows (incluso Windows 10): 394271 |
| .NET Framework 4.6.2   | Nell'Aggiornamento dell'anniversario di Windows 10 e in Windows Server 2016: 394802<br />In tutti gli altri sistemi operativi Windows (inclusi gli altri sistemi operativi Windows 10): 394806 |
| .NET Framework 4.7     | In Windows 10 Creators Update: 460798<br />In tutti gli altri sistemi operativi Windows (inclusi gli altri sistemi operativi Windows 10): 460805 |
| .NET Framework 4.7.1   | In Windows 10 Fall Creators Update e Windows Server, versione 1709: 461308<br/>In tutti gli altri sistemi operativi Windows (inclusi gli altri sistemi operativi Windows 10): 461310 |
| .NET Framework 4.7.2   | In Windows 10 aprile 2018 Update e Windows Server, versione 1803: 461808<br/>In tutti i sistemi operativi Windows diversi da Windows 10 Aprile 2018 Update e Windows Server, versione 1803: 461814 |
| .NET Framework 4.8     | Su Windows 10 maggio 2019 aggiornamento e Windows 10 novembre 2019 aggiornamento: 528040<br/>In Windows 10 e Windows Server, versione 1909: 528209<br/>In tutti gli altri sistemi operativi Windows (inclusi gli altri sistemi operativi Windows 10): 528049 |

### <a name="minimum-version"></a>Versione minima

Per determinare se è presente una versione *minima* di .NET Framework, utilizzare il valore **Release** REG_DWORD più piccolo per tale versione della tabella precedente.

Ad esempio, se l'applicazione viene eseguita in .NET Framework 4.8 o versione successiva, verificare la verifica di un **valore Release** REG_DWORD maggiore *o uguale a* 528040.

| Versione di .NET Framework | Valore minimo |
| ---------------------- | ------------- |
| .NET Framework 4.5     | 378389 |
| .NET Framework 4.5.1   | 378675 |
| .NET Framework 4.5.2   | 379893 |
| .NET Framework 4.6     | 393295 |
| .NET Framework 4.6.1   | 394254 |
| .NET Framework 4.6.2   | 394802 |
| .NET Framework 4.7     | 460798 |
| .NET Framework 4.7.1   | 461308 |
| .NET Framework 4.7.2   | 461808 |
| .NET Framework 4.8     | 528040 |

### <a name="use-registry-editor"></a>Utilizzare l'editor del Registro di sistema

01. Dal menu **Start** scegliere **Esegui**, immettere *regedit* e quindi selezionare **OK**.

    Per eseguire regedit, è necessario avere le credenziali amministrative.

01. Nell'Editor del Registro di sistema aprire la seguente sottochiave: **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**. Se la sottochiave **Full** non è presente, .NET Framework 4.5 o versioni successive non è installato.

01. Verificare la presenza di una voce REG_DWORD denominata **Release**. Se esiste, è installato .NET Framework 4.5 o versione successiva. Il valore corrisponde a una particolare versione di .NET Framework. Nella figura seguente, ad esempio, il valore della voce **Release** è 528040, ovvero la chiave di rilascio per .NET Framework 4.8.

    ![Voce del Registro di sistema per .NET Framework 4.5](./media/clr-installdir.png "Voce del Registro di sistema per .NET Framework 4.5")

### <a name="use-powershell-to-check-for-a-minimum-version"></a>Usare PowerShell per verificare la presenza di una versione minimaUse PowerShell to check for a minimum version

Utilizzare i comandi di PowerShell per controllare il valore della voce **Release** della sottochiave **\\HKEY_LOCAL_MACHINE SOFTWARE Microsoft\\\\NET Framework Setup\\NDP\\v4\\Full.**

Gli esempi seguenti illustrano come verificare il valore della voce **Release** per determinare se .NET Framework 4.6.2 o versioni successive è installato. Questo codice restituisce `True` se è installato e `False` in caso contrario.

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

### <a name="query-the-registry-using-code"></a>Eseguire una query del Registro di sistema utilizzando il codiceQuery the registry using code

01. Utilizzare <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> i <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> metodi e per accedere alla sottochiave **\\HKEY_LOCAL_MACHINE SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** nel Registro di sistema di Windows.

    > [!IMPORTANT]
    > Se l'app in esecuzione è a 32 bit e in esecuzione in Windows a 64 bit, i percorsi del Registro di sistema saranno diversi da quelli elencati in precedenza. Il Registro di sistema a 64 bit è disponibile nella sottochiave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node.\\ ** Ad esempio, la sottochiave del Registro di sistema per .NET Framework 4.5 è **HKEY_LOCAL_MACHINE\\\\SOFTWARE Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**.

01. Controllare il valore **di Release** REG_DWORD per determinare la versione installata. Affinché sia compatibile con la versione attualmente installata, è possibile cercare un valore maggiore o uguale ai valori elencati nella [tabella delle versioni di .NET Framework](#version_table).

L'esempio seguente illustra come verificare il valore della voce **Release** nel Registro di sistema per determinare quale versione di .NET Framework 4.5 e versioni successive è installata:

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

Questo esempio segue la procedura consigliata per il controllo della versione:

- Verifica se il valore della voce **Release** è *maggiore o uguale* al valore delle parole chiave Release note.
- Controlla in ordine dalla versione più recente a quella meno recente.

## <a name="detect-net-framework-10-through-40"></a>Rilevare .NET Framework da 1.0 a 4.0

Ogni versione di .NET Framework compresa tra 1.1 e 4.0 è elencata come sottochiave in **HKEY_LOCAL_MACHINE\\SOFTWARE\\\\Setup\\NDP**. Nella tabella seguente è elencato il percorso di ogni versione di .NET Framework. Per la maggior parte **Install** delle versioni, `1` è disponibile un valore di Installa REG_DWORD per indicare che questa versione è installata. In queste sottochiavi, c'è anche un **Version** REG_SZ valore che contiene una stringa di versione.

> [!NOTE]
> La sottochiave di installazione di **NET Framework** nel percorso del Registro di sistema *non* inizia con un punto.

| Versione Framework  | Sottochiave del Registro di sistema | valore |
| ------------------ | --------------- | ----- |
| 1.0                | **Software\\\\HKLM\\Microsoft . Criteri\\\\NETFramework v1.0\\3705**     | **Installazione** REG_SZ è uguale a`1` |
| 1.1                | **Configurazione\\NDP\\\\\\v1.1.4322 del software HKLM Software\\di Microsoft NET Framework**   | **Installazione** REG_DWORD è uguale a`1` |
| 2.0                | **Configurazione\\\\NDP\\\\v2.0.50727 del software\\HKLM Software di Microsoft NET Framework**  | **Installazione** REG_DWORD è uguale a`1` |
| 3.0                | **Installazione\\NDP\\\\\\v3.0\\del programma di installazione del software HKLM Software\\di Microsoft NET Framework** | **InstallSuccess** REG_DWORD è uguale a`1` |
| 3,5                | **Configurazione\\NDP\\\\\\v3.5 del software HKLM Software\\microsoft NET Framework**        | **Installazione** REG_DWORD è uguale a`1` |
| 4.0 Profilo client | **Client\\NDP\\\\\\v4\\per l'installazione del software HKLM Software\\Microsoft NET Framework**  | **Installazione** REG_DWORD è uguale a`1` |
| 4.0 Profilo completo   | **NDP\\\\NDP\\\\v4\\del programma di installazione\\del software HKLM Software Microsoft NET Framework completo**    | **Installazione** REG_DWORD è uguale a`1` |

> [!IMPORTANT]
> Se l'app in esecuzione è a 32 bit e in esecuzione in Windows a 64 bit, i percorsi del Registro di sistema saranno diversi da quelli elencati in precedenza. Il Registro di sistema a 64 bit è disponibile nella sottochiave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node.\\ ** Ad esempio, la sottochiave del Registro di sistema per .NET Framework 3.5 è **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\NDP\\\\NDP\\v3.5**.

Si noti che il percorso del Registro di sistema per la sottochiave di.NET Framework 1.0 è diverso dagli altri.

### <a name="use-registry-editor-older-framework-versions"></a>Utilizzare l'editor del Registro di sistema (versioni precedenti del framework)

01. Dal menu **Start** scegliere **Esegui**, immettere *regedit* e quindi selezionare **OK**.

    Per eseguire regedit, è necessario avere le credenziali amministrative.

01. Aprire la sottochiave corrispondente alla versione che si desidera controllare. Utilizzare la tabella nella sezione [Rilevare .NET Framework 1.0 a 4.0.](#detect-net-framework-10-through-40)

    Nella figura seguente vengono illustrati la sottochiave e il relativo valore **Version** per .NET Framework 3.5.

    ![Voce del Registro di sistema per .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 e versioni precedenti")

### <a name="query-the-registry-using-code-older-framework-versions"></a>Eseguire una query sul Registro di sistema utilizzando il codice (versioni precedenti del framework)Query the registry using code (older framework versions)

Utilizzare <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> la classe per accedere alla sottochiave NDP di **installazione\\\\\\\\di Microsoft NET Framework SOFTWARE HKEY_LOCAL_MACHINE** nel Registro di sistema di Windows.

> [!IMPORTANT]
> Se l'app in esecuzione è a 32 bit e in esecuzione in Windows a 64 bit, i percorsi del Registro di sistema saranno diversi da quelli elencati in precedenza. Il Registro di sistema a 64 bit è disponibile nella sottochiave **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node.\\ ** Ad esempio, la sottochiave del Registro di sistema per .NET Framework 3.5 è **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\NDP\\\\NDP\\v3.5**.

Nell'esempio seguente vengono trovate le versioni da.NET Framework 1 a 4 installate:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a>Trovare le versioni di CLR

Le versioni di CLR di .NET Framework installate con .NET Framework vengono sottoposte a controllo delle versioni separatamente. Esistono due modi per rilevare la versione di CLR di .NET Framework:

- **Lo strumento Clrver.exe**

  Utilizzare [lo strumento Versione CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) per determinare quali versioni di CLR sono installate in un computer. Aprire il prompt dei comandi `clrver`per gli sviluppatori per Visual [Studio](../tools/developer-command-prompt-for-vs.md) e immettere .

  Output di esempio:

  ```console
  Versions installed on the machine:
  v2.0.50727
  v4.0.30319
  ```

- **La `Environment` classe**

  > [!IMPORTANT]
  > Per .NET Framework 4.5 e versioni successive, non utilizzare la <xref:System.Environment.Version%2A?displayProperty=nameWithType> proprietà per rilevare la versione di CLR. Eseguire invece una query nel Registro di sistema come descritto in [Rilevare .NET Framework 4.5 e versioni successive.](#detect-net-framework-45-and-later-versions)
  
  01. Eseguire la query per la proprietà <xref:System.Environment.Version?displayProperty=nameWithType> per recuperare un oggetto <xref:System.Version>.
  
      L'oggetto `System.Version` identifica la versione del runtime che esegue attualmente il codice. Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere state installate nel computer.
  
      Per .NET Framework versioni 4, 4.5, 4.5.1 e 4.5.2, <xref:System.Version> la rappresentazione di stringa dell'oggetto restituito ha il formato 4.0.30319. *xxxxx*, dove *xxxxx* è minore di 42000. Per .NET Framework 4.6 e versioni successive, ha il formato 4.0.30319.42000.
  
  01. Dopo aver creato l'oggetto **Version,** eseguire una query come segue:
  
      - Per l'identificatore della versione principale (ad esempio, *4* per la versione 4.0), usare la proprietà <xref:System.Version.Major%2A?displayProperty=nameWithType>.
  
      - Per l'identificatore della versione secondaria (ad esempio, *0* per la versione 4.0), usare la proprietà <xref:System.Version.Minor%2A?displayProperty=nameWithType>.
  
      - Per l'intera stringa di versione (ad esempio, *4.0.30319.18010*), usare il metodo <xref:System.Version.ToString%2A?displayProperty=nameWithType>. Questo metodo restituisce un valore singolo che riflette la versione del runtime che esegue il codice. Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere installate nel computer.

  L'esempio seguente usa la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per recuperare le informazioni sulla versione di CLR:
  
  [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
  [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Vedere anche

- [Procedura: determinare quali aggiornamenti di .NET Framework sono installati](how-to-determine-which-net-framework-updates-are-installed.md)
- [Installare .NET Framework per sviluppatori](../install/guide-for-developers.md)
- [Versioni e dipendenze di .NET Framework](versions-and-dependencies.md)
