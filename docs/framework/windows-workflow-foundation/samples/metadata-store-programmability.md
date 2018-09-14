---
title: Programmabilità dell'archivio di metadati
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 4ea6117686b985a9ea18ce4e5cc4ea2b5c25524c
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45512530"
---
# <a name="metadata-store-programmability"></a><span data-ttu-id="4ef6a-102">Programmabilità dell'archivio di metadati</span><span class="sxs-lookup"><span data-stu-id="4ef6a-102">Metadata Store Programmability</span></span>
<span data-ttu-id="4ef6a-103">L'archivio di metadati è una funzionalità di [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] che consente l'associazione di metadati arbitrari, nel formato di attributi CLR, ai tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-103">The metadata store is a [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] feature that allows for the association of arbitrary metadata, in the form of CLR attributes, to types at runtime.</span></span> <span data-ttu-id="4ef6a-104">In questo modo è possibile un accoppiamento libero tra i componenti runtime e le controparti in fase di progettazione e la possibilità di modificare i componenti della fase di progettazione senza incidere sul runtime.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-104">This allows for a loose coupling between the run-time components and their design-time counterparts, as well as the ability to change the design-time components without affecting the runtime.</span></span> <span data-ttu-id="4ef6a-105">In questo esempio viene illustrato come programmare in base all'archivio di metadati applicando attributi a un tipo in fase di esecuzione, ovvero l'origine che non può essere controllata.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-105">The sample shows how to program against the metadata store by applying attributes to a run-time type, the source for which we have no control over.</span></span> <span data-ttu-id="4ef6a-106">Secondo la terminologia usata in genere, un'applicazione host registra i metadati per un set di tipi.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-106">The terminology typically used is that a hosting application registers the metadata for a set of types.</span></span>  
  
 <span data-ttu-id="4ef6a-107">All'interno dell'output, è possibile notare un attributo aggiuntivo imprevisto, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-107">Within the output, you may notice an additional, unexpected attribute, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span></span> <span data-ttu-id="4ef6a-108">Viene aggiunto in caso di utilizzo dell'API dei metadati e non ha alcun impatto sull'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-108">This is added when using the Metadata API and has no impact on the running of the sample.</span></span>  
  
 <span data-ttu-id="4ef6a-109">In questo esempio viene illustrato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4ef6a-109">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4ef6a-110">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="4ef6a-110">Demonstrates</span></span>  
  
-   <span data-ttu-id="4ef6a-111">Inserimento di attributi tramite l'API dell'archivio di metadati.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-111">Attribute injection using the metadata store API.</span></span>  
  
-   <span data-ttu-id="4ef6a-112">Uso di un meccanismo di callback per rinviare la registrazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-112">Using a callback mechanism to defer metadata registration.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4ef6a-113">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="4ef6a-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4ef6a-114">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione ProgrammingMetadataStore.sln.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ProgrammingMetadataStore.sln solution file.</span></span>  
  
2.  <span data-ttu-id="4ef6a-115">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4ef6a-116">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-116">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ef6a-117">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4ef6a-118">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4ef6a-119">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4ef6a-120">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4ef6a-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`