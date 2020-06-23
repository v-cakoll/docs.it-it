---
title: Determinare le versioni di .NET Framework installate
description: Usare il codice, regedit.exe o PowerShell per individuare le versioni di .NET Framework installate in un computer eseguendo una query sul Registro di sistema di Windows.
ms.date: 02/03/2020
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: 122441e9238fd91199aed255b0125f69081c0a8c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990136"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Procedura: Determinare le versioni di .NET Framework installate

Gli utenti possono [installare](../install/index.md) ed eseguire più versioni del .NET Framework nei propri computer. Quando si sviluppa o si distribuisce l'app, potrebbe essere necessario conoscere quali versioni di .NET Framework sono installate nel computer dell'utente. Il registro di sistema contiene un elenco delle versioni .NET Framework installate in un computer.

.NET Framework è costituito da due componenti principali, le cui versioni sono definite separatamente:

- Un set di assembly, ovvero raccolte di tipi e risorse che forniscono la funzionalità per le app. .NET Framework e gli assembly condividono lo stesso numero di versione. Ad esempio, le versioni di .NET Framework includono 4.5, 4.6.1 e 4.7.2.

- Common Language Runtime (CLR), che gestisce ed esegue il codice dell'app In genere una singola versione di CLR supporta più versioni di .NET Framework. Ad esempio CLR Version 4.0.30319. *xxxxx* , dove *xxxxx* è inferiore a 42000, supporta .NET Framework versioni da 4 a 4.5.2. La versione di CLR maggiore o uguale a 4.0.30319.42000 supporta .NET Framework versioni che iniziano con .NET Framework 4,6.

Sono disponibili strumenti gestiti dalla community che consentono di individuare le versioni di .NET Framework installate:

- [https://github.com/jmalarcon/DotNetVersions](https://github.com/jmalarcon/DotNetVersions)

  Strumento da riga di comando .NET 2,0.

- [https://github.com/EliteLoser/DotNetVersionLister](https://github.com/EliteLoser/DotNetVersionLister)

  Un modulo di PowerShell 2,0.

Per informazioni sul rilevamento degli aggiornamenti installati per ogni versione della .NET Framework, vedere [procedura: determinare quali aggiornamenti di .NET Framework sono installati](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="detect-net-framework-45-and-later-versions"></a>Rilevare .NET Framework 4,5 e versioni successive

La versione di .NET Framework (4,5 e versioni successive) installata in un computer è elencata nel registro di sistema in **HKEY_LOCAL_MACHINE \\ software \\ Microsoft \\ NET Framework Setup \\ NDP \\ V4 \\ full**. Se manca la sottochiave completa, .NET Framework 4,5 o **versione** successiva non è installato.

> [!NOTE]
> La sottochiave di **installazione di .NET Framework** nel percorso del registro di sistema *non inizia con* un punto.

Il valore REG_DWORD di **rilascio** nel registro di sistema rappresenta la versione di .NET Framework installata.

<a name="version_table"></a>

| Versione di .NET Framework | Valore della **versione** |
| ---------------------- | -------------------------- |
| .NET Framework 4.5     | Tutti i sistemi operativi Windows: 378389 |
| .NET Framework 4.5.1   | In Windows 8.1 e Windows Server 2012 R2:378675<br />In tutti gli altri sistemi operativi Windows: 378758 |
| .NET Framework 4.5.2   | Tutti i sistemi operativi Windows: 379893 |
| .NET framework 4.6     | In Windows 10:393295<br />In tutti gli altri sistemi operativi Windows: 393297 |
| .NET Framework 4.6.1   | Nei sistemi Windows 10 con aggiornamento di novembre: 394254<br />In tutti gli altri sistemi operativi Windows (incluso Windows 10): 394271 |
| .NET Framework 4.6.2   | Nell'Aggiornamento dell'anniversario di Windows 10 e in Windows Server 2016: 394802<br />In tutti gli altri sistemi operativi Windows (inclusi altri sistemi operativi Windows 10): 394806 |
| .NET Framework 4.7     | In Windows 10 Creators Update: 460798<br />In tutti gli altri sistemi operativi Windows (inclusi altri sistemi operativi Windows 10): 460805 |
| .NET Framework 4.7.1   | In Windows 10 Fall Creators Update e Windows Server versione 1709:461308<br/>In tutti gli altri sistemi operativi Windows (inclusi altri sistemi operativi Windows 10): 461310 |
| .NET Framework 4.7.2   | In Windows 10 aprile 2018 aggiornamento e Windows Server, versione 1803:461808<br/>In tutti i sistemi operativi Windows diversi da Windows 10 aprile 2018 aggiornamento e Windows Server, versione 1803:461814 |
| .NET Framework 4.8     | In Windows 10 maggio 2019 aggiornamento e Windows 10 novembre 2019 aggiornamento: 528040<br/>In Windows 10 maggio 2020 aggiornamento: 528372<br/>In tutti gli altri sistemi operativi Windows (inclusi altri sistemi operativi Windows 10): 528049 |

### <a name="minimum-version"></a>Versione minima

Per determinare se è presente una versione *minima* del .NET Framework, utilizzare il valore di **rilascio** più piccolo REG_DWORD per quella versione della tabella precedente.

Se, ad esempio, l'applicazione viene eseguita con .NET Framework 4,8 o versione successiva, testare un valore di REG_DWORD **versione** *maggiore o uguale a* 528040.

| Versione di .NET Framework | Valore minimo |
| ---------------------- | ------------- |
| .NET Framework 4.5     | 378389 |
| .NET Framework 4.5.1   | 378675 |
| .NET Framework 4.5.2   | 379893 |
| .NET framework 4.6     | 393295 |
| .NET Framework 4.6.1   | 394254 |
| .NET Framework 4.6.2   | 394802 |
| .NET Framework 4.7     | 460798 |
| .NET Framework 4.7.1   | 461308 |
| .NET Framework 4.7.2   | 461808 |
| .NET Framework 4.8     | 528040 |

### <a name="use-registry-editor"></a>Utilizzare l'editor del registro di sistema

01. Dal menu **Start** scegliere **Esegui**, immettere *regedit* e quindi selezionare **OK**.

    Per eseguire regedit, è necessario avere le credenziali amministrative.

01. Nell'editor del registro di sistema aprire la sottochiave seguente: **HKEY_LOCAL_MACHINE \\ software \\ Microsoft \\ NET Framework Setup \\ NDP \\ V4 \\ full**. Se la sottochiave **Full** non è presente, .NET Framework 4.5 o versioni successive non è installato.

01. Verificare la presenza di una voce di REG_DWORD denominata **Release**. Se esiste, è necessario che sia installato .NET Framework 4,5 o versione successiva. Il valore corrisponde a una particolare versione del .NET Framework. Nella figura seguente, ad esempio, il valore della voce di **versione** è 528040, ovvero la chiave di rilascio per .NET Framework 4,8.

    ![Voce del registro di sistema per la .NET Framework 4,5](./media/clr-installdir.png "Voce del registro di sistema per la .NET Framework 4,5")

### <a name="use-powershell-to-check-for-a-minimum-version"></a>Usare PowerShell per verificare la presenza di una versione minima

Usare i comandi di PowerShell per controllare il valore della voce di **rilascio** della sottochiave **completa del \\ software HKEY_LOCAL_MACHINE \\ Microsoft \\ NET Framework Setup \\ NDP \\ V4 \\ ** .

Gli esempi seguenti illustrano come verificare il valore della voce **Release** per determinare se .NET Framework 4.6.2 o versioni successive è installato. Questo codice restituisce `True` se è installato e `False` in caso contrario.

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

### <a name="query-the-registry-using-code"></a>Eseguire query sul Registro di sistema usando il codice

01. Usare i <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> metodi e per accedere alla sottochiave ** \\ completa del software HKEY_LOCAL_MACHINE \\ Microsoft NET Framework per l'installazione di \\ \\ NDP \\ \\ V4** nel registro di sistema di Windows.

    > [!IMPORTANT]
    > Se l'app in esecuzione è a 32 bit e viene eseguita in Windows a 64 bit, i percorsi del registro di sistema saranno diversi da quelli elencati in precedenza. Il registro di sistema a 64 bit è disponibile nella sottochiave ** \\ \\ Wow6432Node \\ software HKEY_LOCAL_MACHINE** . La sottochiave del registro di sistema per .NET Framework 4,5 è ad esempio **HKEY_LOCAL_MACHINE \\ software \\ Wow6432Node \\ Microsoft \\ NET Framework Setup \\ NDP \\ V4 \\ full**.

01. Controllare il valore di REG_DWORD **versione** per determinare la versione installata. Affinché sia compatibile con la versione attualmente installata, è possibile cercare un valore maggiore o uguale ai valori elencati nella [tabella delle versioni di .NET Framework](#version_table).

L'esempio seguente illustra come verificare il valore della voce **Release** nel Registro di sistema per determinare quale versione di .NET Framework 4.5 e versioni successive è installata:

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

Questo esempio segue la procedura consigliata per il controllo della versione:

- Verifica se il valore della voce **Release** è *maggiore o uguale* al valore delle parole chiave Release note.
- Controlla in ordine dalla versione più recente a quella meno recente.

## <a name="detect-net-framework-10-through-40"></a>Rileva .NET Framework da 1,0 a 4,0

Ogni versione di .NET Framework da 1,1 a 4,0 è elencata come sottochiave in **HKEY_LOCAL_MACHINE \\ software \\ Microsoft \\ NET Framework Setup \\ NDP**. La tabella seguente elenca il percorso di ogni versione di .NET Framework. Per la maggior parte delle versioni, viene installato **un valore** di REG_DWORD `1` per indicare che questa versione è installata. In queste sottochiavi è presente anche una **versione** REG_SZ valore che contiene una stringa di versione.

> [!NOTE]
> La sottochiave di **installazione di .NET Framework** nel percorso del registro di sistema *non inizia con* un punto.

| Versione del Framework  | Sottochiave del registro di sistema | valore |
| ------------------ | --------------- | ----- |
| 1.0                | **HKLM \\ software \\ Microsoft \\ . \\Criteri NETFramework \\ v 1.0 \\ 3705**     | **Installa** REG_SZ uguale a`1` |
| 1.1                | **HKLM \\ software \\ Microsoft \\ NET Framework Setup \\ NDP \\ v 1.1.4322**   | **Installa** REG_DWORD uguale a`1` |
| 2.0                | **HKLM \\ software \\ Microsoft \\ NET Framework Setup \\ NDP \\ v 2.0.50727**  | **Installa** REG_DWORD uguale a`1` |
| 3.0                | **Installazione di HKLM \\ software \\ Microsoft \\ NET Framework installazione di \\ NDP \\ v 3.0 \\** | **InstallSuccess** REG_DWORD uguale a`1` |
| 3,5                | **HKLM \\ software \\ Microsoft \\ NET Framework Setup \\ NDP \\ v 3.5**        | **Installa** REG_DWORD uguale a`1` |
| 4,0 profilo client | **HKLM \\ software \\ Microsoft \\ NET Framework Setup \\ NDP \\ V4 \\ client**  | **Installa** REG_DWORD uguale a`1` |
| 4,0 profilo completo   | **HKLM \\ software \\ Microsoft \\ NET Framework installazione di \\ NDP \\ V4 \\ full**    | **Installa** REG_DWORD uguale a`1` |

> [!IMPORTANT]
> Se l'app in esecuzione è a 32 bit e viene eseguita in Windows a 64 bit, i percorsi del registro di sistema saranno diversi da quelli elencati in precedenza. Il registro di sistema a 64 bit è disponibile nella sottochiave ** \\ \\ Wow6432Node \\ software HKEY_LOCAL_MACHINE** . La sottochiave del registro di sistema per .NET Framework 3,5 è ad esempio **HKEY_LOCAL_MACHINE \\ software \\ Wow6432Node \\ Microsoft \\ NET Framework Setup \\ NDP \\ v 3.5**.

Si noti che il percorso del registro di sistema della sottochiave .NET Framework 1,0 è diverso da quello degli altri.

### <a name="use-registry-editor-older-framework-versions"></a>Utilizzare l'editor del registro di sistema (versioni precedenti del Framework)

01. Dal menu **Start** scegliere **Esegui**, immettere *regedit* e quindi selezionare **OK**.

    Per eseguire regedit, è necessario avere le credenziali amministrative.

01. Aprire la sottochiave che corrisponde alla versione che si desidera controllare. Usare la tabella nella sezione [Detect .NET Framework 1,0 through 4,0](#detect-net-framework-10-through-40) .

    Nella figura seguente sono illustrate la sottochiave e il relativo valore di **versione** per .NET Framework 3,5.

    ![Voce del registro di sistema per la .NET Framework 3,5.](./media/net-4-and-earlier.png ".NET Framework 3,5 e versioni precedenti")

### <a name="query-the-registry-using-code-older-framework-versions"></a>Eseguire query sul Registro di sistema usando il codice (versioni precedenti del Framework)

Usare la <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> classe per accedere alla sottochiave del ** \\ programma di installazione di Microsoft NET Framework di HKEY_LOCAL_MACHINE software \\ Microsoft \\ NET Framework \\ ** nel registro di sistema di Windows

> [!IMPORTANT]
> Se l'app in esecuzione è a 32 bit e viene eseguita in Windows a 64 bit, i percorsi del registro di sistema saranno diversi da quelli elencati in precedenza. Il registro di sistema a 64 bit è disponibile nella sottochiave ** \\ \\ Wow6432Node \\ software HKEY_LOCAL_MACHINE** . La sottochiave del registro di sistema per .NET Framework 3,5 è ad esempio **HKEY_LOCAL_MACHINE \\ software \\ Wow6432Node \\ Microsoft \\ NET Framework Setup \\ NDP \\ v 3.5**.

Nell'esempio seguente vengono individuate le .NET Framework da 1 a 4 versioni installate:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a>Trovare le versioni di CLR

Il .NET Framework CLR installato con .NET Framework viene sottoversione separatamente. Esistono due modi per rilevare la versione del .NET Framework CLR:

- **Strumento Clrver.exe**

  Utilizzare lo [strumento versione CLR (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) per determinare quali versioni di CLR sono installate in un computer. Aprire il [prompt dei comandi per gli sviluppatori per Visual Studio](../tools/developer-command-prompt-for-vs.md) e immettere `clrver` .

  Output di esempio:

  ```console
  Versions installed on the machine:
  v2.0.50727
  v4.0.30319
  ```

- **`Environment`Classe**

  > [!IMPORTANT]
  > Per .NET Framework 4,5 e versioni successive, non usare la <xref:System.Environment.Version%2A?displayProperty=nameWithType> proprietà per rilevare la versione di CLR. In alternativa, eseguire una query sul Registro di sistema come descritto in [rilevare .NET Framework 4,5 e versioni successive](#detect-net-framework-45-and-later-versions).
  
  01. Eseguire la query per la proprietà <xref:System.Environment.Version?displayProperty=nameWithType> per recuperare un oggetto <xref:System.Version>.
  
      L'oggetto `System.Version` identifica la versione del runtime che esegue attualmente il codice. Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere state installate nel computer.
  
      Per .NET Framework versioni 4, 4,5, 4.5.1 e 4.5.2, la rappresentazione di stringa dell'oggetto restituito <xref:System.Version> ha il formato 4.0.30319.* xxxxx*, dove *xxxxx* è inferiore a 42000. Per .NET Framework 4,6 e versioni successive, il formato è 4.0.30319.42000.
  
  01. Dopo aver eseguito l'oggetto **versione** , eseguire una query nel modo seguente:
  
      - Per l'identificatore della versione principale (ad esempio, *4* per la versione 4.0), usare la proprietà <xref:System.Version.Major%2A?displayProperty=nameWithType>.
  
      - Per l'identificatore della versione secondaria (ad esempio, *0* per la versione 4.0), usare la proprietà <xref:System.Version.Minor%2A?displayProperty=nameWithType>.
  
      - Per l'intera stringa di versione (ad esempio, *4.0.30319.18010*), usare il metodo <xref:System.Version.ToString%2A?displayProperty=nameWithType>. Questo metodo restituisce un valore singolo che riflette la versione del runtime che esegue il codice. Non restituisce le versioni di assembly o altre versioni del runtime che potrebbero essere installate nel computer.

  L'esempio seguente usa la proprietà <xref:System.Environment.Version%2A?displayProperty=nameWithType> per recuperare le informazioni sulla versione di CLR:
  
  [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
  [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Vedere anche

- [Procedura: determinare gli aggiornamenti di .NET Framework installati](how-to-determine-which-net-framework-updates-are-installed.md)
- [Installare .NET Framework per sviluppatori](../install/guide-for-developers.md)
- [Versioni e dipendenze di .NET Framework](versions-and-dependencies.md)
