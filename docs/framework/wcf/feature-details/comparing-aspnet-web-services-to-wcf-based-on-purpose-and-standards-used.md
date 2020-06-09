---
title: Confronto tra i servizi Web ASP.NET e WCF basato sullo scopo e gli standard usati
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: b27f3516868ec70319ce37fbbd774a29347b0bc8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597579"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Confronto tra i servizi Web ASP.NET e WCF basato sullo scopo e gli standard usati
I servizi Web ASP.NET sono stati sviluppati per creare applicazioni che inviano e ricevono messaggi usando SOAP (Simple Object Access Protocol) su HTTP. La struttura dei messaggi può essere definita usando un XML Schema e viene fornito un strumento per facilitare la serializzazione dei messaggi provenienti e destinati a oggetti .NET Framework. La tecnologia può generare automaticamente metadati per descrivere i servizi Web nel linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) e viene fornito un secondo strumento per generare client per i servizi Web da WSDL.  
  
 WCF consente di consentire a .NET Framework applicazioni di scambiare messaggi con altre entità software. Per impostazione predefinita viene usato SOAP, ma i messaggi possono avere qualsiasi formato ed essere trasmessi mediante qualsiasi protocollo di trasporto. La struttura dei messaggi può essere definita usando un XML Schema e sono disponibili diverse opzioni per la serializzazione dei messaggi provenienti e destinati a oggetti .NET Framework. WCF può generare automaticamente metadati per descrivere le applicazioni compilate utilizzando la tecnologia in WSDL e fornisce anche uno strumento per la generazione di client per tali applicazioni da WSDL.  
  
 Gli standard supportati dai servizi Web di ASP.NET sono documentati in [vantaggi dei servizi Web XML creati con ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100)). L'elenco più completo degli standard supportati da WCF è elencato in [protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Vedere anche

- [Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo](comparing-aspnet-web-services-to-wcf-based-on-development.md)
