---
title: Metodo SqlStreamChars. Write (Char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395584"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a>Metodo SqlStreamChars. Write (Char [], Int32, Int32)

Quando ne viene eseguito l'override in una classe derivata, scrive una sequenza di caratteri nel flusso corrente e sposta in avanti la posizione corrente all'interno del flusso in base al numero di caratteri scritti. L'assembly che contiene questo metodo ha una relazione friend con SQLAccess. dll. È destinato all'uso da SQL Server. Per gli altri database, utilizzare il meccanismo di hosting fornito da tale database.

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a>Parametri

`buffer`  
Matrice di caratteri da scrivere.

`offset`  
Offset relativo all'origine.

`count`  
Numero di caratteri da scrivere nel flusso corrente.

## <a name="remarks"></a>Note

> [!WARNING]
> Il metodo `SqlStreamChars.Write` è privato e non è destinato a essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questo metodo per scrivere in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System. Data. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
