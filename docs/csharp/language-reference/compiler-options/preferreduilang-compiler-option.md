---
title: -preferreduilang (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 7ebafcf446c9033c93e0c5fa5e11ea2930bd2e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602553"
---
# <a name="-preferreduilang-c-compiler-options"></a>-preferreduilang (opzioni del compilatore C#)
Utilizzando l'opzione del compilatore `-preferreduilang`, è possibile specificare la lingua in cui tramite il compilatore C# viene visualizzato l'output, ad esempio i messaggi di errore.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a>Argomenti  
 `language`  
 [Nome](/windows/desktop/Intl/language-names) della lingua da usare per l'output del compilatore.  
  
## <a name="remarks"></a>Osservazioni  
 È possibile utilizzare l'opzione del compilatore `-preferreduilang` per specificare la lingua che si desidera venga utilizzata dal compilatore C# per i messaggi di errore e altri output della riga di comando. Se il Language Pack della lingua non è installato, viene utilizzata l'impostazione della lingua del sistema operativo e non viene segnalato alcun errore.  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>Requisiti  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
