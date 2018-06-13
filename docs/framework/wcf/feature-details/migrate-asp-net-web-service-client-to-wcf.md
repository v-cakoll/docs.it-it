---
title: 'Procedura: eseguire la migrazione del codice per client di servizi Web ASP.NET a Windows Communication Foundation'
ms.date: 03/30/2017
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
ms.openlocfilehash: cb60f9cb2e8f35ee703b049eae9e3d99c1ec7d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491130"
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>Procedura: eseguire la migrazione del codice per client di servizi Web ASP.NET a Windows Communication Foundation
La procedura seguente descrive i passaggi generali da seguire per la migrazione del codice client di servizio Web ASP.NET a WCF.  
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>Per eseguire la migrazione del codice per client di servizi Web ASP.NET a WCF  
  
1.  Assicurarsi che esista un set completo di test per il client.  
  
2.  Utilizzare Visual Studio 2005 per aggiornare l'applicazione client a .NET 2.0. Eseguire il set di test.  
  
3.  Rimuovere il codice del client ASP.NET dal progetto client. Tale codice è presente nei moduli generati tramite lo strumento WSDL.exe.  
  
4.  Generare codice client WCF usando il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Aggiungere il codice al progetto client ed eseguire il merge del risultato della configurazione nel file di configurazione esistente del client.  
  
5.  Compilare l'applicazione. Corregge gli errori di compilazione sostituendo i riferimenti ai tipi di client ASP.NET precedenti con i riferimenti ai nuovi tipi di client WCF.  
  
6.  Eseguire il set di test.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Eseguire la migrazione del codice dei servizi Web ASP.NET in Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
