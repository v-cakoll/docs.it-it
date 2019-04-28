---
title: CoreResponseData.m_ResponseHeaders Field
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
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705974"
---
# <a name="coreresponsedatamresponseheaders-field"></a>CoreResponseData.m\_ResponseHeaders campo

`CoreResponseData.m_ResponseHeaders` è un <xref:System.Net.WebHeaderCollection> di intestazioni associate alla risposta del server.

## <a name="syntax"></a>Sintassi
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> Questa API non deve essere utilizzata direttamente nel codice. È necessario utilizzare invece un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete. Visualizzare [manuale dell'utente di DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Microsoft non supporta l'uso di questa classe in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System. dll)

**Versioni di .NET framework:** Disponibile dalla 2.0.
