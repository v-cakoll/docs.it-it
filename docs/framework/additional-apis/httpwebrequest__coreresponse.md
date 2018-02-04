---
title: HttpWebRequest._CoreResponse Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6493747cf6c894357223f011da026770778e26c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="7dbc1-102">HttpWebRequest. \_CoreResponse campo</span><span class="sxs-lookup"><span data-stu-id="7dbc1-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="7dbc1-103">`HttpWebRequest._CoreResponse`è un oggetto (entrambi un [CoreResponseData](coreresponsedata.md) o <xref:System.Exception>) contenente il risultato dell'analisi delle risposte HTTP.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="7dbc1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7dbc1-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="7dbc1-105">Questa API non deve essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="7dbc1-106">Utilizzare invece un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="7dbc1-107">Vedere [manuale dell'utente DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="7dbc1-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="7dbc1-108">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7dbc1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7dbc1-109">Requirements</span></span>

<span data-ttu-id="7dbc1-110">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7dbc1-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7dbc1-111">**Assembly:** System (System. dll)</span><span class="sxs-lookup"><span data-stu-id="7dbc1-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7dbc1-112">**Versioni di .NET framework:** disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-112">**.NET Framework versions:** Available since 2.0.</span></span>
