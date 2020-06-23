---
title: HttpWebRequest. _CoreResponse campo
description: Vedere il campo HttpWebRequest. _CoreResponse in .NET. Questo campo è un oggetto CoreResponseData o Exception che contiene il risultato dell'analisi della risposta HTTP.
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
ms.openlocfilehash: 5093ec7ed2c3b94931dcd622ae9ccdb42feffa18
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989749"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest. \_ Campo CoreResponse

`HttpWebRequest._CoreResponse`è un oggetto ( [CoreResponseData](coreresponsedata.md) o <xref:System.Exception> ) contenente il risultato dell'analisi della risposta http.

## <a name="syntax"></a>Sintassi
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Questa API non è destinata all'uso diretto nel codice. È invece consigliabile usare un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete. Vedere [il manuale dell'utente di DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
>
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
