---
title: Metodo Exception. PrepForRemoting (System)
author: mairaw
ms.author: mairaw
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 057390d64f70d3cb8eba7d4b29b94570fdca77e3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72405032"
---
# <a name="exceptionprepforremoting-method"></a>Metodo Exception.PrepForRemoting

Conserva la traccia dello stack sul lato server aggiungendola al messaggio prima che l'eccezione venga rigenerata nel sito di chiamata del client.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Valore restituito

<xref:System.Exception>  
Istanza corrente di <xref:System.Exception>.

## <a name="remarks"></a>Note

> [!WARNING]
> Il metodo `Exception.PrepForRemoting` è interno e non è destinato a essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System>

**Assembly:** mscorlib. dll (in mscorlib. dll)

**Versioni .NET Framework:** Disponibile a partire da 1,0.
