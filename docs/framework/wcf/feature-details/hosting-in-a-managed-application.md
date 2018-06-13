---
title: Hosting in un'applicazione gestita
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: f374c199fb1982ab8854e41c0c8308f46451d9d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489742"
---
# <a name="hosting-in-a-managed-application"></a>Hosting in un'applicazione gestita
Servizi Windows Communication Foundation (WCF) possono essere ospitati in qualsiasi [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dell'applicazione. Il self-hosting dei servizi è l'opzione di hosting più flessibile, poiché richiede la distribuzione di un'infrastruttura minima. Tuttavia, è anche l'opzione meno solida, poiché le applicazioni gestite non forniscono la funzionalità di gestione di altre opzioni di hosting in WCF, ad esempio Internet Information Services (IIS) e i servizi Windows e hosting avanzati.  
  
 Per creare un servizio indipendente, creare e aprire un'istanza di <xref:System.ServiceModel.ServiceHost>, che avvia un servizio di ascolto di messaggi. Per altre informazioni, vedere [procedura: ospitare un servizio WCF in un'applicazione gestita da](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Per un esempio completo su come definire un contratto, implementare il contratto e ospitare un servizio all'interno di un'applicazione gestita, vedere il [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md) e [indipendente](../../../../docs/framework/wcf/samples/self-host.md).  
  
 Nelle sezioni seguenti vengono descritti scenari comuni di utilizzo di questa opzione di hosting.  
  
## <a name="console-applications"></a>Applicazioni console  
 Gli scenari comuni di self-hosting consente sono servizi WCF in esecuzione all'interno delle applicazioni console. Hosting di un servizio WCF all'interno di un'applicazione console è in genere utile durante la fase di sviluppo del servizio. Agevola infatti il debug, l'ottenimento di informazioni di traccia per scoprire cosa accadde all'interno dell'applicazione e lo spostamento copiandole in nuove posizioni.  
  
## <a name="rich-client-applications"></a>Applicazioni rich client  
 Altri scenari comuni di self-hosting ci sono applicazioni rich client, quali quelle basate su Windows Presentation Foundation (WPF) o Windows Form (Winform). Questa opzione di hosting consente inoltre ad applicazioni rich client, quali quelle [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] e Windows Form, di comunicare più facilmente con l'esterno. Ad esempio, un client di collaborazione peer-to-peer che utilizza [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] per l'interfaccia utente e ospita anche un servizio WCF che consente ad altri client di connettersi ad esso per condividere informazioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Servizi di hosting](../../../../docs/framework/wcf/hosting-services.md)  
 [Esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md)
