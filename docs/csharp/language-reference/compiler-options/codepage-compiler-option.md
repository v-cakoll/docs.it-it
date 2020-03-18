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
ms.openlocfilehash: 3352e7fc446ace391540360a3b6b36d604ca5f13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173757"
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

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
