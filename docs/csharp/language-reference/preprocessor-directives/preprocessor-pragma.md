---
title: '#pragma - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 65ca38ff6993117b6ed9f716d4ac93ba2d4a9ddf
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605660"
---
# <a name="pragma-c-reference"></a>#pragma (Riferimenti per C#)
`#pragma` fornisce al compilatore istruzioni speciali per la compilazione del file in cui si trova. Le istruzioni devono essere supportate dal compilatore. In altre parole, non è possibile usare `#pragma` per creare istruzioni di pre-elaborazione personalizzate. Il compilatore Microsoft C# supporta le due istruzioni `#pragma` seguenti:  
  
 [avviso #pragma](./preprocessor-pragma-warning.md)  
  
 [checksum #pragma](./preprocessor-pragma-checksum.md)  
  
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

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore C#](./index.md)
- [avviso #pragma](./preprocessor-pragma-warning.md)
- [checksum #pragma](./preprocessor-pragma-checksum.md)
