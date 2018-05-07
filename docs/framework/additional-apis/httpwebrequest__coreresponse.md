---
title: Campo HttpWebRequest._CoreResponse
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 3627c9bf0d72ccec3a0d6d9c7c89b62f83dcd4b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest. \_CoreResponse campo

`HttpWebRequest._CoreResponse` è un oggetto (entrambi una [CoreResponseData](coreresponsedata.md) o un <xref:System.Exception>) contenente il risultato dell'analisi delle risposte HTTP.

## <a name="syntax"></a>Sintassi
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Questa API non deve essere utilizzata direttamente nel codice. Utilizzare invece un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete. Vedere [manuale dell'utente DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Namespace:** <xref:System.Net>

**Assembly:** System (System. dll)

**Versioni di .NET framework:** disponibile dalla 2.0.
