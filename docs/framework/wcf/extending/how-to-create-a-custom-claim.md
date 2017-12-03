---
title: 'Procedura: creare un''attestazione personalizzata'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f0cc23d5b6720d78afdc1acd50a2b84b76b977e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="88c60-102">Procedura: creare un'attestazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="88c60-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="88c60-103">L'infrastruttura del modello di identità in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] fornisce una serie di tipi di attestazione e diritti incorporati, oltre alle funzioni di supporto per la creazione di istanze di <xref:System.IdentityModel.Claims.Claim> con tali tipi e diritti.</span><span class="sxs-lookup"><span data-stu-id="88c60-103">The Identity Model infrastructure in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="88c60-104">Queste attestazioni incorporate sono progettate per modellare le informazioni presenti nei tipi di credenziali client supportati da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="88c60-104">These built-in claims are designed to model information found in client credential types that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports by default.</span></span> <span data-ttu-id="88c60-105">In molti casi, le attestazioni incorporate sono sufficienti; tuttavia alcune applicazioni possono richiedere attestazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="88c60-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="88c60-106">Un'attestazione è costituita dal tipo di attestazione, dalla risorsa a cui si applica l'attestazione e dal diritto asserito sulla risorsa in questione.</span><span class="sxs-lookup"><span data-stu-id="88c60-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="88c60-107">In questo argomento viene descritto come creare un'attestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="88c60-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="88c60-108">Per creare un'attestazione personalizzata basata su un tipo di dati primitivo</span><span class="sxs-lookup"><span data-stu-id="88c60-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1.  <span data-ttu-id="88c60-109">Creare un'attestazione personalizzata passando il tipo di attestazione, il valore della risorsa e il diritto al costruttore <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="88c60-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="88c60-110">Stabilire un valore univoco per il tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="88c60-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="88c60-111">Il tipo di attestazione è un identificatore di stringa univoco.</span><span class="sxs-lookup"><span data-stu-id="88c60-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="88c60-112">È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il tipo di attestazione sia univoco.</span><span class="sxs-lookup"><span data-stu-id="88c60-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="88c60-113">Per un elenco di tipi di attestazione definiti da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere la classe <xref:System.IdentityModel.Claims.ClaimTypes>.</span><span class="sxs-lookup"><span data-stu-id="88c60-113">For a list of claim types that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="88c60-114">Scegliere il tipo di dati primitivo e il valore della risorsa.</span><span class="sxs-lookup"><span data-stu-id="88c60-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="88c60-115">Una risorsa è un oggetto.</span><span class="sxs-lookup"><span data-stu-id="88c60-115">A resource is an object.</span></span> <span data-ttu-id="88c60-116">Il tipo CLR della risorsa può essere primitivo, ad esempio <xref:System.String> o <xref:System.Int32> o qualsiasi tipo serializzabile.</span><span class="sxs-lookup"><span data-stu-id="88c60-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="88c60-117">Il tipo CLR della risorsa deve essere serializzabile, poiché le attestazioni vengono serializzate in diversi punti da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88c60-117">The CLR type of the resource must be serializable, because claims are serialized at various points by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="88c60-118">I tipi primitivi sono serializzabili.</span><span class="sxs-lookup"><span data-stu-id="88c60-118">Primitive types are serializable.</span></span>  
  
    3.  <span data-ttu-id="88c60-119">Scegliere un diritto definito da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o un valore univoco per un diritto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="88c60-119">Choose a right that is defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="88c60-120">Un diritto è un identificatore di stringa univoco.</span><span class="sxs-lookup"><span data-stu-id="88c60-120">A right is a unique string identifier.</span></span> <span data-ttu-id="88c60-121">I diritti definiti da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono definiti nella classe <xref:System.IdentityModel.Claims.Rights>.</span><span class="sxs-lookup"><span data-stu-id="88c60-121">The rights that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="88c60-122">È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il diritto sia univoco.</span><span class="sxs-lookup"><span data-stu-id="88c60-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="88c60-123">Nell'esempio di codice seguente viene creata un'attestazione personalizzata con un tipo di attestazione `http://example.org/claims/simplecustomclaim`, per una risorsa denominata `Driver's License`, e con il diritto <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="88c60-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="88c60-124">Per creare un'attestazione personalizzata basata su un tipo di dati non primitivo</span><span class="sxs-lookup"><span data-stu-id="88c60-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1.  <span data-ttu-id="88c60-125">Creare un'attestazione personalizzata passando il tipo di attestazione, il valore della risorsa e il diritto al costruttore <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="88c60-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="88c60-126">Stabilire un valore univoco per il tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="88c60-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="88c60-127">Il tipo di attestazione è un identificatore di stringa univoco.</span><span class="sxs-lookup"><span data-stu-id="88c60-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="88c60-128">È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il tipo di attestazione sia univoco.</span><span class="sxs-lookup"><span data-stu-id="88c60-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="88c60-129">Per un elenco di tipi di attestazione definiti da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vedere la classe <xref:System.IdentityModel.Claims.ClaimTypes>.</span><span class="sxs-lookup"><span data-stu-id="88c60-129">For a list of claim types that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="88c60-130">Scegliere o definire un tipo non primitivo serializzabile per la risorsa.</span><span class="sxs-lookup"><span data-stu-id="88c60-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="88c60-131">Una risorsa è un oggetto.</span><span class="sxs-lookup"><span data-stu-id="88c60-131">A resource is an object.</span></span> <span data-ttu-id="88c60-132">Il tipo CLR della risorsa deve essere serializzabile, poiché le attestazioni vengono serializzate in diversi punti da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88c60-132">The CLR type of the resource must be serializable, because claims are serialized at various points by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="88c60-133">I tipi primitivi sono già serializzabili.</span><span class="sxs-lookup"><span data-stu-id="88c60-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="88c60-134">Quando viene definito un nuovo tipo, applicare <xref:System.Runtime.Serialization.DataContractAttribute> alla classe.</span><span class="sxs-lookup"><span data-stu-id="88c60-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="88c60-135">Applicare inoltre l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a tutti i membri del nuovo tipo che devono essere serializzati come parte dell'attestazione.</span><span class="sxs-lookup"><span data-stu-id="88c60-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="88c60-136">Nell'esempio di codice seguente viene definito un tipo di risorsa personalizzato denominato `MyResourceType`.</span><span class="sxs-lookup"><span data-stu-id="88c60-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)] 
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]        
  
    3.  <span data-ttu-id="88c60-137">Scegliere un diritto definito da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o un valore univoco per un diritto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="88c60-137">Choose a right that is defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="88c60-138">Un diritto è un identificatore di stringa univoco.</span><span class="sxs-lookup"><span data-stu-id="88c60-138">A right is a unique string identifier.</span></span> <span data-ttu-id="88c60-139">I diritti definiti da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono definiti nella classe <xref:System.IdentityModel.Claims.Rights>.</span><span class="sxs-lookup"><span data-stu-id="88c60-139">The rights that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="88c60-140">È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il diritto sia univoco.</span><span class="sxs-lookup"><span data-stu-id="88c60-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="88c60-141">Nell'esempio di codice seguente viene creata un'attestazione personalizzata con un tipo di attestazione `http://example.org/claims/complexcustomclaim`, per un tipo di risorse personalizzato `MyResourceType`, e con il diritto <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="88c60-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)] 
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]     
  
## <a name="example"></a><span data-ttu-id="88c60-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="88c60-142">Example</span></span>  
 <span data-ttu-id="88c60-143">Nell'esempio di codice seguente viene illustrato come creare un'attestazione personalizzata con un tipo di risorsa primitivo e un'attestazione personalizzata con un tipo di risorsa non primitivo.</span><span class="sxs-lookup"><span data-stu-id="88c60-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="88c60-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88c60-144">See Also</span></span>  
 <xref:System.IdentityModel.Claims.Claim>  
 <xref:System.IdentityModel.Claims.Rights>  
 <xref:System.IdentityModel.Claims.ClaimTypes>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="88c60-145">Gestione attestazioni e autorizzazioni con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="88c60-145">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="88c60-146">Gestione attestazioni e autorizzazioni con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="88c60-146">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
