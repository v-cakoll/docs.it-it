---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 5e157da25829a0741de988d1d6dde0318a93b109
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475286"
---
# <a name="msmq"></a><span data-ttu-id="6500a-102">MSMQ</span><span class="sxs-lookup"><span data-stu-id="6500a-102">MSMQ</span></span>
<span data-ttu-id="6500a-103">In un'applicazione MSMQ, non viene trasferita alcuna attività aggiuntiva dal canale in coda a MSMQ e da MSMQ al canale in coda.</span><span class="sxs-lookup"><span data-stu-id="6500a-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="6500a-104">Inoltre, l'ID messaggio MSMQ e l'ID messaggio SOAP, insieme all'ID attività, se esistente, vengono analizzati come parte delle tracce del canale in coda in un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="6500a-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="6500a-105">l'ID messaggio MSMQ e l'ID messaggio SOAP, insieme all'ID attività, se esistente, vengono analizzati come parte delle tracce del canale in coda in un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="6500a-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="6500a-106">I trasferimenti necessari per l'operazione di ricezione vengono eseguiti in modo simile per qualsiasi altro trasporto (operazione di ricezione byte->elaborazione messaggio->).</span><span class="sxs-lookup"><span data-stu-id="6500a-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
