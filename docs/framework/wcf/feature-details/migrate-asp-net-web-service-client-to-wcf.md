---
title: 'Procedura: eseguire la migrazione del codice per client di servizi Web ASP.NET a Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d77e07cca938b67f5b79416ac4d8fdef96739ed2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="6eaac-102">Procedura: eseguire la migrazione del codice per client di servizi Web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="6eaac-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="6eaac-103">Nella procedura seguente vengono descritti i passaggi generali da eseguire per la migrazione del codice per client di servizi Web ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eaac-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="6eaac-104">Routine</span><span class="sxs-lookup"><span data-stu-id="6eaac-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="6eaac-105">Per eseguire la migrazione del codice per client di servizi Web ASP.NET a WCF</span><span class="sxs-lookup"><span data-stu-id="6eaac-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="6eaac-106">Assicurarsi che esista un set completo di test per il client.</span><span class="sxs-lookup"><span data-stu-id="6eaac-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="6eaac-107">Utilizzare Visual Studio 2005 per aggiornare l'applicazione client a .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="6eaac-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="6eaac-108">Eseguire il set di test.</span><span class="sxs-lookup"><span data-stu-id="6eaac-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="6eaac-109">Rimuovere il codice del client ASP.NET dal progetto client.</span><span class="sxs-lookup"><span data-stu-id="6eaac-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="6eaac-110">Tale codice è presente nei moduli generati tramite lo strumento WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="6eaac-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="6eaac-111">Generare [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] codice client usando il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6eaac-111">Generate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="6eaac-112">Aggiungere il codice al progetto client ed eseguire il merge del risultato della configurazione nel file di configurazione esistente del client.</span><span class="sxs-lookup"><span data-stu-id="6eaac-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="6eaac-113">Compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6eaac-113">Compile the application.</span></span> <span data-ttu-id="6eaac-114">Correggere gli errori di compilazione sostituendo i riferimenti ai tipi di client ASP.NET precedenti con i nuovi tipi di client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eaac-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client types.</span></span>  
  
6.  <span data-ttu-id="6eaac-115">Eseguire il set di test.</span><span class="sxs-lookup"><span data-stu-id="6eaac-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eaac-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6eaac-116">See Also</span></span>  
 [<span data-ttu-id="6eaac-117">Procedura: eseguire la migrazione di codice del servizio Web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="6eaac-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
