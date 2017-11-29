---
title: Messaggi in coda eliminati al secondo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d7386b2f7c6d78dde41c88c66d216b99cc21050
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="8fd72-102">Messaggi in coda eliminati al secondo</span><span class="sxs-lookup"><span data-stu-id="8fd72-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="8fd72-103">Nome contatore: messaggi in coda eliminati al secondo</span><span class="sxs-lookup"><span data-stu-id="8fd72-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8fd72-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8fd72-104">Description</span></span>  
 <span data-ttu-id="8fd72-105">Numero di messaggi eliminati dal trasporto in coda di questo servizio al secondo.</span><span class="sxs-lookup"><span data-stu-id="8fd72-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="8fd72-106">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.</span><span class="sxs-lookup"><span data-stu-id="8fd72-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8fd72-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="8fd72-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
