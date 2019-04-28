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
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="8bb22-102">CoreResponseData.m\_ResponseHeaders campo</span><span class="sxs-lookup"><span data-stu-id="8bb22-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="8bb22-103">`CoreResponseData.m_ResponseHeaders` è un <xref:System.Net.WebHeaderCollection> di intestazioni associate alla risposta del server.</span><span class="sxs-lookup"><span data-stu-id="8bb22-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="8bb22-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8bb22-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="8bb22-105">Questa API non deve essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="8bb22-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="8bb22-106">È necessario utilizzare invece un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete.</span><span class="sxs-lookup"><span data-stu-id="8bb22-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="8bb22-107">Visualizzare [manuale dell'utente di DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="8bb22-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="8bb22-108">Microsoft non supporta l'uso di questa classe in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="8bb22-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="8bb22-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8bb22-109">Requirements</span></span>

<span data-ttu-id="8bb22-110">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="8bb22-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="8bb22-111">**Assembly:** Sistema (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="8bb22-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="8bb22-112">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="8bb22-112">**.NET Framework versions:** Available since 2.0.</span></span>
