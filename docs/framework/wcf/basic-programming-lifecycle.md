---
title: Ciclo di vita della programmazione di base
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: 6d9ea3b877e7c735cf789039b2a6956037372888
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330558"
---
# <a name="basic-programming-lifecycle"></a>Ciclo di vita della programmazione di base
Windows Communication Foundation (WCF) consente alle applicazioni di comunicare se sono nello stesso computer, nella rete Internet o su diverse piattaforme applicative. Questo argomento illustra le attività necessarie per compilare un'applicazione WCF. Per un'applicazione di esempio funzionante, vedere [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Attività di base  
 Le attività di base da eseguire sono descritte di seguito, in ordine progressivo:  
  
1. Definire il contratto di servizio. Un contratto di servizio specifica la firma di un servizio, i dati che scambia e altri dati necessari contrattualmente. Per altre informazioni, vedere [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2. Implementare il contratto. Per implementare un contratto di servizio, creare una classe che implementa il contratto e specificare i comportamenti personalizzati per il runtime. Per altre informazioni, vedere [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3. Configurare il servizio specificando gli endpoint e le informazioni su altri comportamenti. Per altre informazioni, vedere [configurazione dei servizi](../../../docs/framework/wcf/configuring-services.md).  
  
4. Ospitare il servizio. Per altre informazioni, vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).  
  
5. Compilare un'applicazione client. Per altre informazioni, vedere [creazione di client](../../../docs/framework/wcf/building-clients.md).  
  
 Anche se gli argomenti in questa sezione seguono questo ordine, alcuni scenari non partono dall'inizio. Ad esempio, se si desidera compilare un client per un servizio preesistente, iniziare dal passaggio 5. Se invece si compila un servizio che altri utilizzeranno, è possibile ignorare il passaggio 5.  
  
 Una volta acquisita familiarità con lo sviluppo di contratti di servizio, è anche possibile leggere [Introduzione all'estendibilità](../../../docs/framework/wcf/introduction-to-extensibility.md). Se hai problemi con il servizio, controllare [Guida rapida di risoluzione dei problemi di WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) per vedere se altri hanno problemi uguali o simili.  
  
## <a name="see-also"></a>Vedere anche

- [Implementazione dei contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md)
