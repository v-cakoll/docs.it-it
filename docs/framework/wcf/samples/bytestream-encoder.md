---
title: Codificatore ByteStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0984d3989d6441c363730454ea65b0393c94b9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="bytestream-encoder"></a><span data-ttu-id="ba854-102">Codificatore ByteStream</span><span class="sxs-lookup"><span data-stu-id="ba854-102">ByteStream Encoder</span></span>
<span data-ttu-id="ba854-103">In questo esempio descritto come creare una `ByteStreamHttpBinding`, una <xref:System.ServiceModel.Channels.Binding> che dimostra la funzionalità del codificatore del flusso di byte.</span><span class="sxs-lookup"><span data-stu-id="ba854-103">This sample demonstrates how to create a `ByteStreamHttpBinding`, a <xref:System.ServiceModel.Channels.Binding> that demonstrates the functionality of the byte stream encoder.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ba854-104">Discussione</span><span class="sxs-lookup"><span data-stu-id="ba854-104">Discussion</span></span>  
 <span data-ttu-id="ba854-105">In questo esempio viene descritto come creare un oggetto <xref:System.ServiceModel.Channels.Binding> standard usando gli elementi di associazione standard <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> e <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ba854-105">This sample demonstrates how to create a standard <xref:System.ServiceModel.Channels.Binding> using the standard binding elements <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span> <span data-ttu-id="ba854-106">In questo esempio viene illustrato come usare il codificatore del flusso di byte per caricare e scaricare un'immagine.</span><span class="sxs-lookup"><span data-stu-id="ba854-106">This sample shows how to use the byte stream encoder to upload and download an image.</span></span> <span data-ttu-id="ba854-107">La funzionalità di codificatore del flusso di byte supporta solo il trasporto HTTP e non supporta funzionalità quali la messaggistica affidabile o la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ba854-107">The byte stream encoder feature only supports the HTTP transport and it does not support features such as reliable messaging or security.</span></span> <span data-ttu-id="ba854-108">L'unica <xref:System.ServiceModel.Channels.MessageVersion> supportata è <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba854-108">The only <xref:System.ServiceModel.Channels.MessageVersion> supported is <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba854-109">Se si esegue questo esempio in [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] o [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], verificare di eseguire [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="ba854-109">If you are running this sample in [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] or [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], ensure that you are running [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with elevated privileges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba854-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ba854-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ba854-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ba854-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ba854-112">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba854-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ba854-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ba854-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ba854-114">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ba854-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ba854-115">Aprire il file ByteStreamHttpBinding.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba854-115">Open the ByteStreamHttpBinding.sln file in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="ba854-116">Avviare una nuova istanza del progetto ByteStreamHttpBindingServer facendo clic sul progetto in Esplora soluzioni e selezionando **Debug**e quindi **Avvia nuova istanza** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="ba854-116">Start a new instance of the ByteStreamHttpBindingServer project by right-clicking the project in the Solution Explorer and selecting **Debug**, and then **Start new instance** from the context menu.</span></span>  
  
3.  <span data-ttu-id="ba854-117">Avviare una nuova istanza del progetto ByteStreamHttpBindingClient facendo clic sul progetto in Esplora soluzioni e selezionando **Debug**, **Avvia nuova istanza** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="ba854-117">Start a new instance of the ByteStreamHttpBindingClient project by right-clicking the project in the Solution Explorer and selecting **Debug**, **Start new instance** from the context menu.</span></span>
