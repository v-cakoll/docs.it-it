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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 712f8a7a153d7255275ff7ebaa647d5a624f8ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a><span data-ttu-id="bebaf-102">Confronto di transazioni in COM+ e ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bebaf-102">Comparing Transactions in COM+ and ServiceModel</span></span>
<span data-ttu-id="bebaf-103">In questo argomento viene illustrato come simulare il comportamento di un servizio COM+ transazionale usando gli attributi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] forniti dallo spazio dei nomi <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="bebaf-103">This topic discusses how to simulate the behavior of a transactional COM+ service using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
## <a name="emulating-com-using-servicemodel-attributes"></a><span data-ttu-id="bebaf-104">Emulazione di COM+ mediante attributi ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bebaf-104">Emulating COM+ Using ServiceModel Attributes</span></span>  
 <span data-ttu-id="bebaf-105">Nella tabella seguente viene confrontata l'enumerazione <xref:System.EnterpriseServices.TransactionOption> usata per creare una transazione `EnterpriseServices` e la modalità di correlazione agli attributi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] forniti dallo spazio dei nomi <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="bebaf-105">The following table compares the <xref:System.EnterpriseServices.TransactionOption> enumeration used to create an `EnterpriseServices` transaction and how they correlate to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
|<span data-ttu-id="bebaf-106">Attributo COM+</span><span class="sxs-lookup"><span data-stu-id="bebaf-106">COM+ attribute</span></span>|<span data-ttu-id="bebaf-107">Attributi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bebaf-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes</span></span>|  
|---------------------|------------------------------------------------------------------------|  
|<span data-ttu-id="bebaf-108">RequiresNew</span><span class="sxs-lookup"><span data-stu-id="bebaf-108">RequiresNew</span></span>|<span data-ttu-id="bebaf-109"><xref:System.ServiceModel.TransactionFlowAttribute> è impostato su <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span><span class="sxs-lookup"><span data-stu-id="bebaf-109"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span></span><br /><br /> <span data-ttu-id="bebaf-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="bebaf-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="bebaf-111">L'attributo `TransactionFlow` nell'elemento di associazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="bebaf-111">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="bebaf-112">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="bebaf-112">Required</span></span>|<span data-ttu-id="bebaf-113"><xref:System.ServiceModel.TransactionFlowAttribute> è impostato su <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span><span class="sxs-lookup"><span data-stu-id="bebaf-113"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span></span><br /><br /> <span data-ttu-id="bebaf-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="bebaf-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="bebaf-115">L'attributo `TransactionFlow` nell'elemento di associazione è `true`.</span><span class="sxs-lookup"><span data-stu-id="bebaf-115">The `TransactionFlow` attribute in the binding element is `true`.</span></span>|  
|<span data-ttu-id="bebaf-116">Supportato</span><span class="sxs-lookup"><span data-stu-id="bebaf-116">Supported</span></span>|<span data-ttu-id="bebaf-117">Non esiste alcun equivalente diretto.</span><span class="sxs-lookup"><span data-stu-id="bebaf-117">There is no direct equivalent.</span></span> <span data-ttu-id="bebaf-118">In generale, è necessario adottare il comportamento specificato per `Required`.</span><span class="sxs-lookup"><span data-stu-id="bebaf-118">In general, you should adopt the behavior specified for `Required` instead.</span></span>|  
|<span data-ttu-id="bebaf-119">NotSupported</span><span class="sxs-lookup"><span data-stu-id="bebaf-119">NotSupported</span></span>|<span data-ttu-id="bebaf-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="bebaf-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `false`.</span></span><br /><br /> <span data-ttu-id="bebaf-121">L'attributo `TransactionFlow` nell'elemento di associazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="bebaf-121">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="bebaf-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="bebaf-122">Disabled</span></span>|<span data-ttu-id="bebaf-123">Non esiste alcun equivalente diretto.</span><span class="sxs-lookup"><span data-stu-id="bebaf-123">There is no direct equivalent.</span></span> <span data-ttu-id="bebaf-124">In generale, è necessario adottare il comportamento specificato per `NotSupported`.</span><span class="sxs-lookup"><span data-stu-id="bebaf-124">In general, you should adopt the behavior specified for `NotSupported` instead.</span></span>|
