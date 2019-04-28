---
title: Classe CoreResponseData
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 640a925c3aec86b4743b1b2b62eb3793af1cc0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675416"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="7d29f-102">Classe CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="7d29f-102">CoreResponseData Class</span></span>

<span data-ttu-id="7d29f-103">Il `CoreResponseData` classe rappresenta il processo di analisi di intestazioni HTTP e il corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="7d29f-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d29f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d29f-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="7d29f-105">Questa API è interna e non deve essere usati direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="7d29f-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="7d29f-106">È necessario utilizzare invece un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete.</span><span class="sxs-lookup"><span data-stu-id="7d29f-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="7d29f-107">Visualizzare [manuale dell'utente di DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="7d29f-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="7d29f-108">Microsoft non supporta l'uso di questa classe in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="7d29f-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d29f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d29f-109">Requirements</span></span>

<span data-ttu-id="7d29f-110">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="7d29f-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="7d29f-111">**Assembly:** Sistema (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="7d29f-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="7d29f-112">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="7d29f-112">**.NET Framework versions:** Available since 2.0.</span></span>
