---
title: Confronto tra i servizi Web ASP.NET e WCF basato sullo scopo e gli standard usati
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 60f2e9ccbfd5dbf205f3ed570ece1d4169f21e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Confronto tra i servizi Web ASP.NET e WCF basato sullo scopo e gli standard usati
I servizi Web ASP.NET sono stati sviluppati per creare applicazioni che inviano e ricevono messaggi usando SOAP (Simple Object Access Protocol) su HTTP. La struttura dei messaggi può essere definita usando un XML Schema e viene fornito un strumento per facilitare la serializzazione dei messaggi provenienti e destinati a oggetti .NET Framework. La tecnologia può generare automaticamente metadati per descrivere i servizi Web nel linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) e viene fornito un secondo strumento per generare client per i servizi Web da WSDL.  
  
 WCF è progettato per consentire applicazioni di .NET Framework scambiare messaggi con altre entità software. Per impostazione predefinita viene usato SOAP, ma i messaggi possono avere qualsiasi formato ed essere trasmessi mediante qualsiasi protocollo di trasporto. La struttura dei messaggi può essere definita usando un XML Schema e sono disponibili diverse opzioni per la serializzazione dei messaggi provenienti e destinati a oggetti .NET Framework. WCF può generare automaticamente metadati per descrivere applicazioni compilate usando la tecnologia in WSDL e fornisce anche uno strumento per la generazione di client per tali applicazioni da WSDL.  
  
 Gli standard supportati dai servizi Web ASP.NET sono documentati in [servizi Web XML creati tramite ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872). L'elenco più dettagliato di standard supportati da WCF sono elencati in [protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Confronto tra servizi Web ASP.NET e WCF in base allo sviluppo](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
