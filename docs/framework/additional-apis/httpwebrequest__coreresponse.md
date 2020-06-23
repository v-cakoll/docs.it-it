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
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="3d304-104">HttpWebRequest. \_ Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="3d304-104">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="3d304-105">`HttpWebRequest._CoreResponse`è un oggetto ( [CoreResponseData](coreresponsedata.md) o <xref:System.Exception> ) contenente il risultato dell'analisi della risposta http.</span><span class="sxs-lookup"><span data-stu-id="3d304-105">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="3d304-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d304-106">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="3d304-107">Questa API non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="3d304-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="3d304-108">È invece consigliabile usare un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete.</span><span class="sxs-lookup"><span data-stu-id="3d304-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="3d304-109">Vedere [il manuale dell'utente di DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="3d304-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="3d304-110">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="3d304-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3d304-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d304-111">Requirements</span></span>

<span data-ttu-id="3d304-112">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3d304-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3d304-113">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="3d304-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="3d304-114">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="3d304-114">**.NET Framework versions:** Available since 2.0.</span></span>
