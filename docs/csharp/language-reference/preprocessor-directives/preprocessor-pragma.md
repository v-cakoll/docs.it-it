---
title: '#pragma - Riferimenti per C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 3bd62364aeae0f21715711324655ef7d00d88afc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712455"
---
# <a name="pragma-c-reference"></a>#pragma (Riferimenti per C#)
`#pragma` fornisce al compilatore istruzioni speciali per la compilazione del file in cui si trova. Le istruzioni devono essere supportate dal compilatore. In altre parole, non è possibile usare `#pragma` per creare istruzioni di pre-elaborazione personalizzate. Il compilatore Microsoft C# supporta le due istruzioni `#pragma` seguenti:  
  
 [avviso #pragma](./preprocessor-pragma-warning.md)  
  
 [Checksum #pragma](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a>Parametri  
 `pragma-name`  
 Nome di un pragma riconosciuto.  
  
 `pragma-arguments`  
 Argomenti specifici del pragma.  
  
## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore di C](./index.md)
- [avviso #pragma](./preprocessor-pragma-warning.md)
- [Checksum #pragma](./preprocessor-pragma-checksum.md)
