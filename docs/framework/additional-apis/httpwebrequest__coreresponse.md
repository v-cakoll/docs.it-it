---
title: HttpWebRequest. _CoreResponse campo
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
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740455"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="4afd2-102">HttpWebRequest.\_campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="4afd2-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="4afd2-103">`HttpWebRequest._CoreResponse` è un oggetto, ovvero [CoreResponseData](coreresponsedata.md) o <xref:System.Exception>, che contiene il risultato dell'analisi della risposta http.</span><span class="sxs-lookup"><span data-stu-id="4afd2-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="4afd2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4afd2-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="4afd2-105">Questa API non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="4afd2-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="4afd2-106">È invece consigliabile usare un <xref:System.Diagnostics.DiagnosticSource> per collegare il codice di rete.</span><span class="sxs-lookup"><span data-stu-id="4afd2-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="4afd2-107">Vedere [il manuale dell'utente di DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="4afd2-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="4afd2-108">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="4afd2-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4afd2-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4afd2-109">Requirements</span></span>

<span data-ttu-id="4afd2-110">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4afd2-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4afd2-111">**Assembly:** System (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="4afd2-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="4afd2-112">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="4afd2-112">**.NET Framework versions:** Available since 2.0.</span></span>
