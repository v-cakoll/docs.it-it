---
title: Record di rilevamento personalizzati
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: d4733b4ffc0d866cf90fd5a5e7d649de261c45fb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499121"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="28d7c-102">Record di rilevamento personalizzati</span><span class="sxs-lookup"><span data-stu-id="28d7c-102">Custom Tracking Records</span></span>

<span data-ttu-id="28d7c-103">In questo argomento viene illustrato come creare record di rilevamento personalizzati e come popolarli con dati da creare insieme ai record.</span><span class="sxs-lookup"><span data-stu-id="28d7c-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>

## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="28d7c-104">Creazione di record di rilevamento personalizzati</span><span class="sxs-lookup"><span data-stu-id="28d7c-104">Emitting Custom Tracking Records</span></span>

<span data-ttu-id="28d7c-105">I record di rilevamento personalizzati possono essere creati da un'attività del codice come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="28d7c-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<span data-ttu-id="28d7c-106">Un oggetto <xref:System.Activities.Tracking.CustomTrackingRecord> viene creato in un'attività del codice richiamando il metodo <xref:System.Activities.NativeActivityContext.Track%2A> su `ActivityContext`.</span><span class="sxs-lookup"><span data-stu-id="28d7c-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActivityContext`.</span></span>

## <a name="see-also"></a><span data-ttu-id="28d7c-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28d7c-107">See also</span></span>

- [<span data-ttu-id="28d7c-108">Monitoraggio dell'infrastruttura di App di Windows Server</span><span class="sxs-lookup"><span data-stu-id="28d7c-108">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="28d7c-109">Monitoraggio delle applicazioni con App Fabric</span><span class="sxs-lookup"><span data-stu-id="28d7c-109">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
