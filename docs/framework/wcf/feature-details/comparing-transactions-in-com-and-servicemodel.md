---
title: Confronto di transazioni in COM+ e ServiceModel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5229c872c4843df916cf538b7f2e88e451dc6b9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a><span data-ttu-id="e1323-102">Confronto di transazioni in COM+ e ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e1323-102">Comparing Transactions in COM+ and ServiceModel</span></span>
<span data-ttu-id="e1323-103">In questo argomento viene illustrato come simulare il comportamento di un servizio COM+ transazionale usando gli attributi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] forniti dallo spazio dei nomi <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="e1323-103">This topic discusses how to simulate the behavior of a transactional COM+ service using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
## <a name="emulating-com-using-servicemodel-attributes"></a><span data-ttu-id="e1323-104">Emulazione di COM+ mediante attributi ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e1323-104">Emulating COM+ Using ServiceModel Attributes</span></span>  
 <span data-ttu-id="e1323-105">Nella tabella seguente viene confrontata l'enumerazione <xref:System.EnterpriseServices.TransactionOption> usata per creare una transazione `EnterpriseServices` e la modalità di correlazione agli attributi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] forniti dallo spazio dei nomi <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="e1323-105">The following table compares the <xref:System.EnterpriseServices.TransactionOption> enumeration used to create an `EnterpriseServices` transaction and how they correlate to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
|<span data-ttu-id="e1323-106">Attributo COM+</span><span class="sxs-lookup"><span data-stu-id="e1323-106">COM+ attribute</span></span>|<span data-ttu-id="e1323-107">Attributi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1323-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes</span></span>|  
|---------------------|------------------------------------------------------------------------|  
|<span data-ttu-id="e1323-108">RequiresNew</span><span class="sxs-lookup"><span data-stu-id="e1323-108">RequiresNew</span></span>|<span data-ttu-id="e1323-109"><xref:System.ServiceModel.TransactionFlowAttribute> è impostato su <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span><span class="sxs-lookup"><span data-stu-id="e1323-109"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span></span><br /><br /> <span data-ttu-id="e1323-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="e1323-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="e1323-111">L'attributo `TransactionFlow` nell'elemento di associazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="e1323-111">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="e1323-112">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="e1323-112">Required</span></span>|<span data-ttu-id="e1323-113"><xref:System.ServiceModel.TransactionFlowAttribute> è impostato su <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span><span class="sxs-lookup"><span data-stu-id="e1323-113"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span></span><br /><br /> <span data-ttu-id="e1323-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="e1323-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="e1323-115">L'attributo `TransactionFlow` nell'elemento di associazione è `true`.</span><span class="sxs-lookup"><span data-stu-id="e1323-115">The `TransactionFlow` attribute in the binding element is `true`.</span></span>|  
|<span data-ttu-id="e1323-116">Supportato</span><span class="sxs-lookup"><span data-stu-id="e1323-116">Supported</span></span>|<span data-ttu-id="e1323-117">Non esiste alcun equivalente diretto.</span><span class="sxs-lookup"><span data-stu-id="e1323-117">There is no direct equivalent.</span></span> <span data-ttu-id="e1323-118">In generale, è necessario adottare il comportamento specificato per `Required`.</span><span class="sxs-lookup"><span data-stu-id="e1323-118">In general, you should adopt the behavior specified for `Required` instead.</span></span>|  
|<span data-ttu-id="e1323-119">NotSupported</span><span class="sxs-lookup"><span data-stu-id="e1323-119">NotSupported</span></span>|<span data-ttu-id="e1323-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="e1323-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `false`.</span></span><br /><br /> <span data-ttu-id="e1323-121">L'attributo `TransactionFlow` nell'elemento di associazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="e1323-121">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="e1323-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="e1323-122">Disabled</span></span>|<span data-ttu-id="e1323-123">Non esiste alcun equivalente diretto.</span><span class="sxs-lookup"><span data-stu-id="e1323-123">There is no direct equivalent.</span></span> <span data-ttu-id="e1323-124">In generale, è necessario adottare il comportamento specificato per `NotSupported`.</span><span class="sxs-lookup"><span data-stu-id="e1323-124">In general, you should adopt the behavior specified for `NotSupported` instead.</span></span>|
