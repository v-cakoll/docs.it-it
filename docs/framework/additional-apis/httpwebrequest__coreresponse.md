---
title: HttpWebRequest._CoreResponse Campo
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
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155921"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="679c4-102">HttpWebRequest. \_Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="679c4-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="679c4-103">`HttpWebRequest._CoreResponse`è un oggetto [(coreResponseData](coreresponsedata.md) <xref:System.Exception>o un ) contenente il risultato dell'analisi della risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="679c4-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="679c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="679c4-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="679c4-105">Questa API non deve essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="679c4-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="679c4-106">Al contrario, <xref:System.Diagnostics.DiagnosticSource> è necessario utilizzare un per eseguire l'hook del codice di rete.</span><span class="sxs-lookup"><span data-stu-id="679c4-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="679c4-107">Vedere [Manuale dell'utente](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)di DiagnosticSource .</span><span class="sxs-lookup"><span data-stu-id="679c4-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="679c4-108">Microsoft non supporta in nessun caso l'utilizzo di questa classe in un'applicazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="679c4-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="679c4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="679c4-109">Requirements</span></span>

<span data-ttu-id="679c4-110">**Spazio dei nomi:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="679c4-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="679c4-111">**Assemblaggio:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="679c4-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="679c4-112">Versioni di **.NET Framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="679c4-112">**.NET Framework versions:** Available since 2.0.</span></span>
