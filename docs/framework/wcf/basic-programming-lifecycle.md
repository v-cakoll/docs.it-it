---
title: Ciclo di vita della programmazione di base
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: b20167ad776f3524e4516b71e43ab8cdb5c2aea4
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="basic-programming-lifecycle"></a>Ciclo di vita della programmazione di base
Windows Communication Foundation (WCF) consente alle applicazioni di comunicare se si trovino nello stesso computer, in Internet o su diverse piattaforme applicative. In questo argomento vengono delineate le attività necessarie per compilare un'applicazione WCF. Per un'applicazione di esempio funzionante, vedere [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Attività di base  
 Le attività di base da eseguire sono descritte di seguito, in ordine progressivo:  
  
1.  Definire il contratto di servizio. Un contratto di servizio specifica la firma di un servizio, i dati che scambia e altri dati necessari contrattualmente. Per altre informazioni, vedere [progettazione contratti di servizio](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2.  Implementare il contratto. Per implementare un contratto di servizio, creare una classe che implementa il contratto e specificare i comportamenti personalizzati per il runtime. Per altre informazioni, vedere [implementare contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3.  Configurare il servizio specificando gli endpoint e le informazioni su altri comportamenti. Per ulteriori informazioni, vedere [configurazione dei servizi](../../../docs/framework/wcf/configuring-services.md).  
  
4.  Ospitare il servizio. Per altre informazioni, vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).  
  
5.  Compilare un'applicazione client. Per altre informazioni, vedere [creazione di client](../../../docs/framework/wcf/building-clients.md).  
  
 Anche se gli argomenti in questa sezione seguono questo ordine, alcuni scenari non partono dall'inizio. Ad esempio, se si desidera compilare un client per un servizio preesistente, iniziare dal passaggio 5. Se invece si compila un servizio che altri utilizzeranno, è possibile ignorare il passaggio 5.  
  
 Una volta acquisita familiarità con lo sviluppo dei contratti di servizio, è inoltre possibile leggere [Introduzione all'estendibilità](../../../docs/framework/wcf/introduction-to-extensibility.md). Se si verificano problemi con il servizio, controllare [Guida rapida risoluzione dei problemi di WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) per vedere se altri utenti hanno problemi identici o simili.  
  
## <a name="see-also"></a>Vedere anche  
 [Implementazione dei contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md)
