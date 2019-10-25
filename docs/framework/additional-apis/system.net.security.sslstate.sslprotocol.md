---
title: Proprietà SslState. SslProtocol (System .NET. Security)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 6983ac071dad29b240308031ecd0a3562a6856e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847199"
---
# <a name="sslstatesslprotocol-property"></a>Proprietà SslState. SslProtocol

Ottiene le versioni del protocollo SSL.

## <a name="syntax"></a>Sintassi

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a>Valore proprietà

<xref:System.Security.Authentication.SslProtocols>  
Combinazione bit per bit dei valori di enumerazione che specificano le versioni del protocollo SSL.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `SslState.SslProtocol` proprietà è interno e non deve essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net.Security>

**Assembly:** System (in System. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
