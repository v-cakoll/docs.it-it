---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 5e157da25829a0741de988d1d6dde0318a93b109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663726"
---
# <a name="msmq"></a>MSMQ
In un'applicazione MSMQ, non viene trasferita alcuna attività aggiuntiva dal canale in coda a MSMQ e da MSMQ al canale in coda.  
  
 Inoltre, l'ID messaggio MSMQ e l'ID messaggio SOAP, insieme all'ID attività, se esistente, vengono analizzati come parte delle tracce del canale in coda in un'operazione di invio.  
  
 l'ID messaggio MSMQ e l'ID messaggio SOAP, insieme all'ID attività, se esistente, vengono analizzati come parte delle tracce del canale in coda in un'operazione di ricezione.  
  
 I trasferimenti necessari per l'operazione di ricezione vengono eseguiti in modo analogo a qualsiasi altro trasporto (ricezione byte -> elaborazione messaggio -> operazione).
