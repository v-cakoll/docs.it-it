---
title: Metodo Exception. PrepForRemoting (System)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214890"
---
# <a name="exceptionprepforremoting-method"></a>Metodo Exception.PrepForRemoting

Conserva la traccia dello stack sul lato server aggiungendola al messaggio prima che l'eccezione venga rigenerata nel sito di chiamata del client.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Valori di codice restituiti

<xref:System.Exception>  
Istanza corrente di <xref:System.Exception>.

## <a name="remarks"></a>Osservazioni

> [!WARNING]
> Il `Exception.PrepForRemoting` metodo è interno e non deve essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System>

**Assembly:** mscorlib. dll (in mscorlib. dll)

**Versioni .NET Framework:** Disponibile a partire da 1,0.
