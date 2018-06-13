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
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a><span data-ttu-id="e5a0f-102">Procedura: eseguire la migrazione del codice per client di servizi Web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e5a0f-102">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="e5a0f-103">La procedura seguente descrive i passaggi generali da seguire per la migrazione del codice client di servizio Web ASP.NET a WCF.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-103">The following procedure describes the broad steps that need to be followed to migrate ASP.NET Web Service client code to WCF.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="e5a0f-104">Routine</span><span class="sxs-lookup"><span data-stu-id="e5a0f-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a><span data-ttu-id="e5a0f-105">Per eseguire la migrazione del codice per client di servizi Web ASP.NET a WCF</span><span class="sxs-lookup"><span data-stu-id="e5a0f-105">To migrate ASP.NET Web Service client code to WCF</span></span>  
  
1.  <span data-ttu-id="e5a0f-106">Assicurarsi che esista un set completo di test per il client.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-106">Ensure that a comprehensive set of tests exist for the client.</span></span>  
  
2.  <span data-ttu-id="e5a0f-107">Utilizzare Visual Studio 2005 per aggiornare l'applicazione client a .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-107">Use Visual Studio 2005 to upgrade the client application to .NET 2.0.</span></span> <span data-ttu-id="e5a0f-108">Eseguire il set di test.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-108">Run the set of tests.</span></span>  
  
3.  <span data-ttu-id="e5a0f-109">Rimuovere il codice del client ASP.NET dal progetto client.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-109">Remove ASP.NET client code from the client project.</span></span> <span data-ttu-id="e5a0f-110">Tale codice è presente nei moduli generati tramite lo strumento WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-110">That code is in modules generated using the WSDL.exe tool.</span></span>  
  
4.  <span data-ttu-id="e5a0f-111">Generare codice client WCF usando il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e5a0f-111">Generate WCF client code using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="e5a0f-112">Aggiungere il codice al progetto client ed eseguire il merge del risultato della configurazione nel file di configurazione esistente del client.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-112">Add that code to the client project and merge the configuration output into the client’s existing configuration file.</span></span>  
  
5.  <span data-ttu-id="e5a0f-113">Compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-113">Compile the application.</span></span> <span data-ttu-id="e5a0f-114">Corregge gli errori di compilazione sostituendo i riferimenti ai tipi di client ASP.NET precedenti con i riferimenti ai nuovi tipi di client WCF.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-114">Repair the compilation errors by replacing references to the former ASP.NET client types with references to the new WCF client types.</span></span>  
  
6.  <span data-ttu-id="e5a0f-115">Eseguire il set di test.</span><span class="sxs-lookup"><span data-stu-id="e5a0f-115">Run the set of tests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a0f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5a0f-116">See Also</span></span>  
 [<span data-ttu-id="e5a0f-117">Procedura: Eseguire la migrazione del codice dei servizi Web ASP.NET in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e5a0f-117">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
