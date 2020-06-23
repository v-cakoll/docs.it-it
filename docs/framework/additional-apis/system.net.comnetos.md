---
title: Classe comnetos (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990400"
---
# <a name="comnetos-class"></a><span data-ttu-id="fd3bb-102">Classe ComNetOS</span><span class="sxs-lookup"><span data-stu-id="fd3bb-102">ComNetOS class</span></span>

<span data-ttu-id="fd3bb-103">Fornisce informazioni sul sistema operativo corrente, ad esempio la versione e il tipo di installazione (client o server).</span><span class="sxs-lookup"><span data-stu-id="fd3bb-103">Provides information about the current operating system, such as its version and installation type (client or server).</span></span> <span data-ttu-id="fd3bb-104">Questa classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="fd3bb-104">This class cannot be inherited.</span></span>
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> <span data-ttu-id="fd3bb-105">Questa classe è interna e non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="fd3bb-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="fd3bb-106">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="fd3bb-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="iswin7orlater-field"></a><span data-ttu-id="fd3bb-107">Campo IsWin7orLater</span><span class="sxs-lookup"><span data-stu-id="fd3bb-107">IsWin7orLater field</span></span>

<span data-ttu-id="fd3bb-108">Specifica se la versione del sistema operativo è Windows 7 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="fd3bb-108">Specifies whether the operating system version is Windows 7 or later.</span></span>

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a><span data-ttu-id="fd3bb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd3bb-109">Requirements</span></span>

<span data-ttu-id="fd3bb-110">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="fd3bb-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="fd3bb-111">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="fd3bb-111">**Assembly:** System (in System.dll)</span></span>
