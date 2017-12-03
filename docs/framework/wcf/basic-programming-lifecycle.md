---
title: Ciclo di vita della programmazione di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 78ad1159232ecfb75745dd72b7da1e3153a79574
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="basic-programming-lifecycle"></a>Ciclo di vita della programmazione di base
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] consente alle applicazioni di comunicare nello stesso computer, in Internet o tra piattaforme di applicazione diverse. In questo argomento vengono delineate le attività necessarie per compilare un'applicazione [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Per un'applicazione di esempio funzionante, vedere [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Attività di base  
 Le attività di base da eseguire sono descritte di seguito, in ordine progressivo:  
  
1.  Definire il contratto di servizio. Un contratto di servizio specifica la firma di un servizio, i dati che scambia e altri dati necessari contrattualmente. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Progettazione contratti di servizio](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2.  Implementare il contratto. Per implementare un contratto di servizio, creare una classe che implementa il contratto e specificare i comportamenti personalizzati per il runtime. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Implementazione dei contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3.  Configurare il servizio specificando gli endpoint e le informazioni su altri comportamenti. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Configurazione dei servizi](../../../docs/framework/wcf/configuring-services.md).  
  
4.  Ospitare il servizio. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Servizi di hosting](../../../docs/framework/wcf/hosting-services.md).  
  
5.  Compilare un'applicazione client. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Generazione di client](../../../docs/framework/wcf/building-clients.md).  
  
 Anche se gli argomenti in questa sezione seguono questo ordine, alcuni scenari non partono dall'inizio. Ad esempio, se si desidera compilare un client per un servizio preesistente, iniziare dal passaggio 5. Se invece si compila un servizio che altri utilizzeranno, è possibile ignorare il passaggio 5.  
  
 Una volta acquisita familiarità con lo sviluppo dei contratti di servizio, è inoltre possibile leggere [Introduzione all'estendibilità](../../../docs/framework/wcf/introduction-to-extensibility.md). Se si verificano problemi con il servizio, controllare [Guida rapida risoluzione dei problemi di WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) per vedere se altri utenti hanno problemi identici o simili.  
  
## <a name="see-also"></a>Vedere anche  
 [Implementazione dei contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md)
