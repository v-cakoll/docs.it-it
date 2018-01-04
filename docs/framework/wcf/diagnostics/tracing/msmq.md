---
title: MSMQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e72d3e400440b830b689f476753a7c8c40fe2586
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="msmq"></a>MSMQ
In un'applicazione MSMQ, non viene trasferita alcuna attività aggiuntiva dal canale in coda a MSMQ e da MSMQ al canale in coda.  
  
 Inoltre, l'ID messaggio MSMQ e l'ID messaggio SOAP, insieme all'ID attività, se esistente, vengono analizzati come parte delle tracce del canale in coda in un'operazione di invio.  
  
 l'ID messaggio MSMQ e l'ID messaggio SOAP, insieme all'ID attività, se esistente, vengono analizzati come parte delle tracce del canale in coda in un'operazione di ricezione.  
  
 I trasferimenti necessari per l'operazione di ricezione vengono eseguiti in modo simile per qualsiasi altro trasporto (operazione di ricezione byte->elaborazione messaggio->).
