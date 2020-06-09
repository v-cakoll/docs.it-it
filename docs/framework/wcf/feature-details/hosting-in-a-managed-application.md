---
title: Hosting in un'applicazione gestita
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 759257edf89d1af5c453bb98f41361b54cf113ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597345"
---
# <a name="hosting-in-a-managed-application"></a>Hosting in un'applicazione gestita
I servizi Windows Communication Foundation (WCF) possono essere ospitati in qualsiasi applicazione .NET Framework. Il self-hosting dei servizi è l'opzione di hosting più flessibile, poiché richiede la distribuzione di un'infrastruttura minima. Tuttavia, è anche l'opzione di hosting meno affidabile, perché le applicazioni gestite non forniscono le funzionalità di hosting e gestione avanzate di altre opzioni di hosting in WCF, ad esempio Internet Information Services (IIS) e i servizi Windows.  
  
 Per creare un servizio indipendente, creare e aprire un'istanza di <xref:System.ServiceModel.ServiceHost>, che avvia un servizio di ascolto di messaggi. Per altre informazioni, vedere [procedura: ospitare un servizio WCF in un'applicazione gestita](../how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Per un esempio completo su come definire un contratto, implementare il contratto e ospitare un servizio all'interno di un'applicazione gestita, vedere l' [esercitazione Introduzione](../getting-started-tutorial.md) e il [self-host](../samples/self-host.md).  
  
 Nelle sezioni seguenti vengono descritti scenari comuni di utilizzo di questa opzione di hosting.  
  
## <a name="console-applications"></a>Applicazioni console  
 Scenari comuni che consentono l'hosting automatico sono i servizi WCF in esecuzione all'interno di applicazioni console. L'hosting di un servizio WCF all'interno di un'applicazione console è in genere utile durante la fase di sviluppo del servizio. Agevola infatti il debug, l'ottenimento di informazioni di traccia per scoprire cosa accadde all'interno dell'applicazione e lo spostamento copiandole in nuove posizioni.  
  
## <a name="rich-client-applications"></a>Applicazioni rich client  
 Altri scenari comuni di self-hosting sono le applicazioni rich client, ad esempio quelle basate su Windows Presentation Foundation (WPF) o Windows Forms (WinForms). Questa opzione di hosting semplifica inoltre la comunicazione tra le applicazioni rich client, ad esempio le applicazioni WPF e Windows Form con il mondo esterno. Ad esempio, un client di collaborazione peer-to-peer che utilizza WPF per la relativa interfaccia utente e ospita anche un servizio WCF che consente ad altri client di connettersi ad esso e condividere le informazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi di hosting](../hosting-services.md)
- [Esercitazione Introduzione](../getting-started-tutorial.md)
