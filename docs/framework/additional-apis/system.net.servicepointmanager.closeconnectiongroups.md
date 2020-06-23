---
title: Metodo ServicePointManager. CloseConnectionGroups (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.CloseConnectionGroups
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: aae9a389ae35e249d43c9dc830a68ec32cf4afef
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990367"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a><span data-ttu-id="2f260-102">ServicePointManager. CloseConnectionGroups, metodo</span><span class="sxs-lookup"><span data-stu-id="2f260-102">ServicePointManager.CloseConnectionGroups method</span></span>

<span data-ttu-id="2f260-103">Scorre tutti i punti di servizio e chiude i gruppi di connessione con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="2f260-103">Iterates through all service points and closes connection groups that have the specified name.</span></span>

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> <span data-ttu-id="2f260-104">Questo metodo è interno e non è destinato a essere utilizzato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="2f260-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2f260-105">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="2f260-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="2f260-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f260-106">Parameters</span></span>

<span data-ttu-id="2f260-107">`connectionGroupName` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="2f260-107">`connectionGroupName` <xref:System.String></span></span>

<span data-ttu-id="2f260-108">Nome del gruppo di connessione da chiudere.</span><span class="sxs-lookup"><span data-stu-id="2f260-108">The name of the connection group to close.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f260-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f260-109">Requirements</span></span>

<span data-ttu-id="2f260-110">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2f260-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2f260-111">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="2f260-111">**Assembly:** System (in System.dll)</span></span>
