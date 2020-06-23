---
title: Metodo Exception. PrepForRemoting (System)
description: Esaminare il metodo Exception. PrepForRemoting in .NET. Il metodo aggiunge l'analisi dello stack sul lato server al messaggio prima che l'eccezione venga rigenerata nel client.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105266"
---
# <a name="exceptionprepforremoting-method"></a>Metodo Exception.PrepForRemoting

Conserva la traccia dello stack sul lato server aggiungendola al messaggio prima che l'eccezione venga rigenerata nel sito di chiamata del client.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Restituisce

<xref:System.Exception>  
Istanza corrente di <xref:System.Exception>.

## <a name="remarks"></a>Commenti

> [!WARNING]
> Il `Exception.PrepForRemoting` metodo è interno e non è destinato a essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System>

**Assembly:** mscorlib.dll (in mscorlib.dll)

**Versioni .NET Framework:** Disponibile a partire da 1,0.
