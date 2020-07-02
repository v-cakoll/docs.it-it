---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614798"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>Le analisi dello stack ottenute quando si usano file PDB portatili ora includono informazioni su file di origine e righe, se richieste

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.7.2, le analisi dello stack ottenute quando si usano file PDB portatili includono informazioni su file di origine e righe, se richieste. Nelle versioni precedenti a .NET Framework 4.7.2 le informazioni su file di origine e righe non sono disponibili quando si usano file PDB portatili, anche se richieste in modo esplicito.

#### <a name="suggestion"></a>Suggerimento

Per le applicazioni destinate a .NET Framework 4.7.2 è possibile rifiutare esplicitamente le informazioni su file di origine e righe quando si usano file PDB portatili, nel caso non siano opportune, aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

Per le applicazioni destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.7.2 o versioni successive, è possibile acconsentire esplicitamente alle informazioni su file di origine e righe quando si usano file PDB portatili aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
