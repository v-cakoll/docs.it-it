---
title: "Estensibilità delle associazioni"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3a59a9529d7f7dbc40978803ffcac6e2f5e088b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="binding-extensibility"></a><span data-ttu-id="f4ace-102">Estensibilità delle associazioni</span><span class="sxs-lookup"><span data-stu-id="f4ace-102">Binding Extensibility</span></span>

<span data-ttu-id="f4ace-103">Contenuto della sezione sono inclusi esempi che illustrano l'associazione personalizzata in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4ace-103">This section contains samples that demonstrate custom binding in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4ace-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f4ace-104">In This Section</span></span>  
 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="f4ace-105">Viene illustrato come implementare un'associazione che posiziona <xref:System.ServiceModel.Channels.HttpTransportBindingElement> o <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> in cima allo stack di <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="f4ace-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 [<span data-ttu-id="f4ace-106">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f4ace-106">WSStreamedHttpBinding</span></span>](wsstreamedhttpbinding.md)  
 <span data-ttu-id="f4ace-107">Nell'esempio viene illustrato come creare un'associazione progettata per supportare scenari basati sul flusso quando viene usato il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="f4ace-107">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
