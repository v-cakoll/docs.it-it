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
ms.openlocfilehash: 39a14a3df5059cc47cd4879e4d4ba351cc7b655b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79156116"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="09ec6-102">Classe CoreResponseData</span><span class="sxs-lookup"><span data-stu-id="09ec6-102">CoreResponseData Class</span></span>

<span data-ttu-id="09ec6-103">La `CoreResponseData` classe rappresenta l'analisi delle intestazioni HTTP e del corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="09ec6-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="09ec6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09ec6-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="09ec6-105">Questa API è interna e non deve essere usata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="09ec6-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="09ec6-106">Al contrario, <xref:System.Diagnostics.DiagnosticSource> è necessario utilizzare un per eseguire l'hook del codice di rete.</span><span class="sxs-lookup"><span data-stu-id="09ec6-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="09ec6-107">Vedere [Manuale dell'utente](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)di DiagnosticSource .</span><span class="sxs-lookup"><span data-stu-id="09ec6-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="09ec6-108">Microsoft non supporta in nessun caso l'utilizzo di questa classe in un'applicazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="09ec6-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="09ec6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09ec6-109">Requirements</span></span>

<span data-ttu-id="09ec6-110">**Spazio dei nomi:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="09ec6-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="09ec6-111">**Assemblaggio:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="09ec6-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="09ec6-112">Versioni di **.NET Framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="09ec6-112">**.NET Framework versions:** Available since 2.0.</span></span>
