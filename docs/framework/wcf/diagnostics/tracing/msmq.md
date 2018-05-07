---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 5e157da25829a0741de988d1d6dde0318a93b109
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="msmq"></a>MSMQ
In un'applicazione MSMQ, non viene trasferita alcuna attività aggiuntiva dal canale in coda a MSMQ e da MSMQ al canale in coda.  
  
 Inoltre, l'ID messaggio MSMQ e l'ID messaggio SOAP, insieme all'ID attività, se esistente, vengono analizzati come parte delle tracce del canale in coda in un'operazione di invio.  
  
 l'ID messaggio MSMQ e l'ID messaggio SOAP, insieme all'ID attività, se esistente, vengono analizzati come parte delle tracce del canale in coda in un'operazione di ricezione.  
  
 I trasferimenti necessari per l'operazione di ricezione vengono eseguiti in modo simile per qualsiasi altro trasporto (operazione di ricezione byte->elaborazione messaggio->).
