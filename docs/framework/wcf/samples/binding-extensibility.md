---
title: Estensibilità delle associazioni
ms.date: 03/30/2017
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
ms.openlocfilehash: af9736a1011c3de6e1add51e8a913745cfd6756d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498974"
---
# <a name="binding-extensibility"></a><span data-ttu-id="a0d50-102">Estensibilità delle associazioni</span><span class="sxs-lookup"><span data-stu-id="a0d50-102">Binding Extensibility</span></span>

<span data-ttu-id="a0d50-103">In questa sezione è inclusi esempi che illustrano l'associazione personalizzata in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a0d50-103">This section contains samples that demonstrate custom binding in Windows Communication Foundation (WCF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0d50-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a0d50-104">In This Section</span></span>  
 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="a0d50-105">Viene illustrato come implementare un'associazione che posiziona <xref:System.ServiceModel.Channels.HttpTransportBindingElement> o <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> in cima allo stack di <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a0d50-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 [<span data-ttu-id="a0d50-106">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a0d50-106">WSStreamedHttpBinding</span></span>](wsstreamedhttpbinding.md)  
 <span data-ttu-id="a0d50-107">Nell'esempio viene illustrato come creare un'associazione progettata per supportare scenari basati sul flusso quando viene usato il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="a0d50-107">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
