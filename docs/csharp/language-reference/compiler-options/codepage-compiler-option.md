---
title: -codepage (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 59dc1abc3f678a4cf15543c11f9f200ff318ce8f
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876919"
---
# <a name="-codepage-c-compiler-options"></a>-codepage (opzioni del compilatore C#)
Questa opzione specifica la tabella codici da usare durante la compilazione, se la pagina richiesta non è la tabella codici predefinita corrente per il sistema.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argomenti  
 `id`  
 ID della tabella codici da usare per tutti i file di codice sorgente nella compilazione.  
  
## <a name="remarks"></a>Osservazioni  
 Il compilatore tenterà innanzitutto di interpretare tutti i file di origine come UTF-8. Se i file del codice sorgente sono codificati con una codifica diversa da UTF-8 e usano caratteri diversi dai caratteri ASCII a 7 bit, usare l'opzione **-codepage** per specificare la tabella codici da usare. **-codepage** si applica a tutti i file di codice sorgente nella compilazione.  
    
 Per informazioni su come individuare le tabelle codici supportate nel sistema, vedere [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
