---
title: Campo CoreResponseData.m_ResponseHeaders
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 723df6dc2de978695608d106e3a01bde286fc4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156103"
---
# <a name="coreresponsedatam_responseheaders-field"></a>CoreResponseData.m\_ResponseHeaders Campo

`CoreResponseData.m_ResponseHeaders`è <xref:System.Net.WebHeaderCollection> una delle intestazioni associate alla risposta del server.

## <a name="syntax"></a>Sintassi
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> Questa API non deve essere utilizzata direttamente nel codice. Al contrario, <xref:System.Diagnostics.DiagnosticSource> è necessario utilizzare un per eseguire l'hook del codice di rete. Vedere [Manuale dell'utente](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)di DiagnosticSource .
>
> Microsoft non supporta in nessun caso l'utilizzo di questa classe in un'applicazione di produzione.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:**<xref:System.Net>

**Assemblaggio:** Sistema (in System.dll)

Versioni di **.NET Framework:** Disponibile dalla 2.0.
