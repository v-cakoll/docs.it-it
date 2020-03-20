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
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="5dd7a-102">CoreResponseData.m\_ResponseHeaders Campo</span><span class="sxs-lookup"><span data-stu-id="5dd7a-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="5dd7a-103">`CoreResponseData.m_ResponseHeaders`è <xref:System.Net.WebHeaderCollection> una delle intestazioni associate alla risposta del server.</span><span class="sxs-lookup"><span data-stu-id="5dd7a-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="5dd7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5dd7a-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="5dd7a-105">Questa API non deve essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="5dd7a-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="5dd7a-106">Al contrario, <xref:System.Diagnostics.DiagnosticSource> è necessario utilizzare un per eseguire l'hook del codice di rete.</span><span class="sxs-lookup"><span data-stu-id="5dd7a-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="5dd7a-107">Vedere [Manuale dell'utente](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)di DiagnosticSource .</span><span class="sxs-lookup"><span data-stu-id="5dd7a-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="5dd7a-108">Microsoft non supporta in nessun caso l'utilizzo di questa classe in un'applicazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="5dd7a-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5dd7a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5dd7a-109">Requirements</span></span>

<span data-ttu-id="5dd7a-110">**Spazio dei nomi:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="5dd7a-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="5dd7a-111">**Assemblaggio:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="5dd7a-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="5dd7a-112">Versioni di **.NET Framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="5dd7a-112">**.NET Framework versions:** Available since 2.0.</span></span>
