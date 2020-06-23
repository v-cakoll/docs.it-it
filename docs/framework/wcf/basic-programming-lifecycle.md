---
title: Ciclo di vita della programmazione di base
description: Informazioni sulle attività per la compilazione di un'applicazione WCF. WCF consente alle app di comunicare sullo stesso computer, su reti o su diverse piattaforme applicative.
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: c672827fff780fd263f5355520bb6ccf02bb902e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245531"
---
# <a name="basic-programming-lifecycle"></a>Ciclo di vita della programmazione di base
Windows Communication Foundation (WCF) consente alle applicazioni di comunicare se si trovano nello stesso computer, in Internet o su diverse piattaforme applicative. In questo argomento vengono descritte le attività necessarie per compilare un'applicazione WCF. Per un'applicazione di esempio funzionante, vedere [Introduzione esercitazione](getting-started-tutorial.md).  
  
## <a name="the-basic-tasks"></a>Attività di base  
 Le attività di base da eseguire sono descritte di seguito, in ordine progressivo:  
  
1. Definire il contratto di servizio. Un contratto di servizio specifica la firma di un servizio, i dati che scambia e altri dati necessari contrattualmente. Per ulteriori informazioni, vedere [progettazione di contratti di servizio](designing-service-contracts.md).  
  
2. Implementare il contratto. Per implementare un contratto di servizio, creare una classe che implementa il contratto e specificare i comportamenti personalizzati per il runtime. Per ulteriori informazioni, vedere [implementazione di contratti di servizio](implementing-service-contracts.md).  
  
3. Configurare il servizio specificando gli endpoint e le informazioni su altri comportamenti. Per ulteriori informazioni, vedere [configurazione dei servizi](configuring-services.md).  
  
4. Ospitare il servizio. Per ulteriori informazioni, vedere [servizi di hosting](hosting-services.md).  
  
5. Compilare un'applicazione client. Per ulteriori informazioni, vedere la pagina relativa alla [compilazione dei client](building-clients.md).  
  
 Anche se gli argomenti in questa sezione seguono questo ordine, alcuni scenari non partono dall'inizio. Ad esempio, se si desidera compilare un client per un servizio preesistente, iniziare dal passaggio 5. Se invece si compila un servizio che altri utilizzeranno, è possibile ignorare il passaggio 5.  
  
 Una volta acquisita familiarità con lo sviluppo di contratti di servizio, è anche possibile leggere [Introduzione all'estendibilità](introduction-to-extensibility.md). In caso di problemi con il servizio, controllare la [Guida introduttiva alla risoluzione dei](wcf-troubleshooting-quickstart.md) problemi di WCF per verificare se altri utenti hanno problemi identici o simili.  
  
## <a name="see-also"></a>Vedere anche

- [Implementazione dei contratti di servizio](implementing-service-contracts.md)
