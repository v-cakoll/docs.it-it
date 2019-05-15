---
title: Hosting in un'applicazione gestita
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: c1f4d91994ba44407ff5c93dbd34aa0bdef9332b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591741"
---
# <a name="hosting-in-a-managed-application"></a>Hosting in un'applicazione gestita
Servizi Windows Communication Foundation (WCF) possono essere ospitati in qualsiasi applicazione .NET Framework. Il self-hosting dei servizi è l'opzione di hosting più flessibile, poiché richiede la distribuzione di un'infrastruttura minima. Tuttavia, è anche l'opzione meno solida, infatti, le applicazioni gestite non forniscono l'hosting avanzati e funzionalità di gestione delle altre opzioni di hosting in WCF, ad esempio servizi Internet Information Services (IIS) e Windows.  
  
 Per creare un servizio indipendente, creare e aprire un'istanza di <xref:System.ServiceModel.ServiceHost>, che avvia un servizio di ascolto di messaggi. Per altre informazioni, vedere [Procedura: Ospitare un servizio WCF in un'applicazione gestita](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Per un esempio completo su come definire un contratto, implementare il contratto e ospitare un servizio all'interno di un'applicazione gestita, vedere la [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md) e il [self-hosting](../../../../docs/framework/wcf/samples/self-host.md).  
  
 Nelle sezioni seguenti vengono descritti scenari comuni di utilizzo di questa opzione di hosting.  
  
## <a name="console-applications"></a>Applicazioni console  
 Scenari comuni che consente il Self-hosting sono servizi WCF in esecuzione all'interno delle applicazioni console. Hosting di un servizio WCF all'interno di un'applicazione console è in genere utile durante la fase di sviluppo del servizio. Agevola infatti il debug, l'ottenimento di informazioni di traccia per scoprire cosa accadde all'interno dell'applicazione e lo spostamento copiandole in nuove posizioni.  
  
## <a name="rich-client-applications"></a>Applicazioni rich client  
 Altri scenari comuni di self-hosting ci sono applicazioni rich client, ad esempio quelle basate su Windows Presentation Foundation (WPF) o Windows Form (WinForms). Questa opzione di hosting consente inoltre ad applicazioni rich client, quali quelle [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] e Windows Form, di comunicare più facilmente con l'esterno. Ad esempio, un client di collaborazione peer-to-peer che utilizza [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] come interfaccia utente e ospita anche un servizio WCF che consente ad altri client di connettersi e condividere informazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi di hosting](../../../../docs/framework/wcf/hosting-services.md)
- [Esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md)
