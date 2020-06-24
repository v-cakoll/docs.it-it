---
title: "Procedura: creare un'attestazione personalizzata"
description: Informazioni su come creare un'attestazione personalizzata in WCF. WCF supporta un'ampia gamma di attestazioni predefinite e alcune applicazioni possono richiedere attestazioni personalizzate.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: 89f2b1359b48b71720db6ff38f27883745cfe612
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247546"
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="b14f2-104">Procedura: creare un'attestazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="b14f2-104">How to: Create a Custom Claim</span></span>
<span data-ttu-id="b14f2-105">L'infrastruttura del modello di identità in Windows Communication Foundation (WCF) fornisce un set di tipi di attestazioni e diritti predefiniti con le funzioni di supporto per la creazione di <xref:System.IdentityModel.Claims.Claim> istanze con tali tipi e diritti.</span><span class="sxs-lookup"><span data-stu-id="b14f2-105">The Identity Model infrastructure in Windows Communication Foundation (WCF) provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="b14f2-106">Queste attestazioni predefinite sono progettate per modellare le informazioni disponibili nei tipi di credenziali client supportate da WCF per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b14f2-106">These built-in claims are designed to model information found in client credential types that WCF supports by default.</span></span> <span data-ttu-id="b14f2-107">In molti casi, le attestazioni incorporate sono sufficienti; tuttavia alcune applicazioni possono richiedere attestazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="b14f2-107">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="b14f2-108">Un'attestazione è costituita dal tipo di attestazione, dalla risorsa a cui si applica l'attestazione e dal diritto asserito sulla risorsa in questione.</span><span class="sxs-lookup"><span data-stu-id="b14f2-108">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="b14f2-109">In questo argomento viene descritto come creare un'attestazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b14f2-109">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="b14f2-110">Per creare un'attestazione personalizzata basata su un tipo di dati primitivo</span><span class="sxs-lookup"><span data-stu-id="b14f2-110">To create a custom claim that is based on a primitive data type</span></span>  
  
1. <span data-ttu-id="b14f2-111">Creare un'attestazione personalizzata passando il tipo di attestazione, il valore della risorsa e il diritto al costruttore <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="b14f2-111">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="b14f2-112">Stabilire un valore univoco per il tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="b14f2-112">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="b14f2-113">Il tipo di attestazione è un identificatore di stringa univoco.</span><span class="sxs-lookup"><span data-stu-id="b14f2-113">The claim type is a unique string identifier.</span></span> <span data-ttu-id="b14f2-114">È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il tipo di attestazione sia univoco.</span><span class="sxs-lookup"><span data-stu-id="b14f2-114">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="b14f2-115">Per un elenco dei tipi di attestazione definiti da WCF, vedere la <xref:System.IdentityModel.Claims.ClaimTypes> classe.</span><span class="sxs-lookup"><span data-stu-id="b14f2-115">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="b14f2-116">Scegliere il tipo di dati primitivo e il valore della risorsa.</span><span class="sxs-lookup"><span data-stu-id="b14f2-116">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="b14f2-117">Una risorsa è un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b14f2-117">A resource is an object.</span></span> <span data-ttu-id="b14f2-118">Il tipo CLR della risorsa può essere primitivo, ad esempio <xref:System.String> o <xref:System.Int32> o qualsiasi tipo serializzabile.</span><span class="sxs-lookup"><span data-stu-id="b14f2-118">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="b14f2-119">Il tipo CLR della risorsa deve essere serializzabile, poiché le attestazioni vengono serializzate in diversi punti da WCF.</span><span class="sxs-lookup"><span data-stu-id="b14f2-119">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="b14f2-120">I tipi primitivi sono serializzabili.</span><span class="sxs-lookup"><span data-stu-id="b14f2-120">Primitive types are serializable.</span></span>  
  
    3. <span data-ttu-id="b14f2-121">Scegliere un diritto definito da WCF o un valore univoco per un diritto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b14f2-121">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="b14f2-122">Un diritto è un identificatore di stringa univoco.</span><span class="sxs-lookup"><span data-stu-id="b14f2-122">A right is a unique string identifier.</span></span> <span data-ttu-id="b14f2-123">I diritti definiti da WCF sono definiti nella <xref:System.IdentityModel.Claims.Rights> classe.</span><span class="sxs-lookup"><span data-stu-id="b14f2-123">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="b14f2-124">È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il diritto sia univoco.</span><span class="sxs-lookup"><span data-stu-id="b14f2-124">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="b14f2-125">Nell'esempio di codice seguente viene creata un'attestazione personalizzata con un tipo di attestazione `http://example.org/claims/simplecustomclaim`, per una risorsa denominata `Driver's License`, e con il diritto <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="b14f2-125">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="b14f2-126">Per creare un'attestazione personalizzata basata su un tipo di dati non primitivo</span><span class="sxs-lookup"><span data-stu-id="b14f2-126">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1. <span data-ttu-id="b14f2-127">Creare un'attestazione personalizzata passando il tipo di attestazione, il valore della risorsa e il diritto al costruttore <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="b14f2-127">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="b14f2-128">Stabilire un valore univoco per il tipo di attestazione.</span><span class="sxs-lookup"><span data-stu-id="b14f2-128">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="b14f2-129">Il tipo di attestazione è un identificatore di stringa univoco.</span><span class="sxs-lookup"><span data-stu-id="b14f2-129">The claim type is a unique string identifier.</span></span> <span data-ttu-id="b14f2-130">È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il tipo di attestazione sia univoco.</span><span class="sxs-lookup"><span data-stu-id="b14f2-130">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="b14f2-131">Per un elenco dei tipi di attestazione definiti da WCF, vedere la <xref:System.IdentityModel.Claims.ClaimTypes> classe.</span><span class="sxs-lookup"><span data-stu-id="b14f2-131">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="b14f2-132">Scegliere o definire un tipo non primitivo serializzabile per la risorsa.</span><span class="sxs-lookup"><span data-stu-id="b14f2-132">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="b14f2-133">Una risorsa è un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b14f2-133">A resource is an object.</span></span> <span data-ttu-id="b14f2-134">Il tipo CLR della risorsa deve essere serializzabile, poiché le attestazioni vengono serializzate in diversi punti da WCF.</span><span class="sxs-lookup"><span data-stu-id="b14f2-134">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="b14f2-135">I tipi primitivi sono già serializzabili.</span><span class="sxs-lookup"><span data-stu-id="b14f2-135">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="b14f2-136">Quando viene definito un nuovo tipo, applicare <xref:System.Runtime.Serialization.DataContractAttribute> alla classe.</span><span class="sxs-lookup"><span data-stu-id="b14f2-136">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="b14f2-137">Applicare inoltre l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a tutti i membri del nuovo tipo che devono essere serializzati come parte dell'attestazione.</span><span class="sxs-lookup"><span data-stu-id="b14f2-137">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="b14f2-138">Nell'esempio di codice seguente viene definito un tipo di risorsa personalizzato denominato `MyResourceType`.</span><span class="sxs-lookup"><span data-stu-id="b14f2-138">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)]
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]
  
    3. <span data-ttu-id="b14f2-139">Scegliere un diritto definito da WCF o un valore univoco per un diritto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b14f2-139">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="b14f2-140">Un diritto è un identificatore di stringa univoco.</span><span class="sxs-lookup"><span data-stu-id="b14f2-140">A right is a unique string identifier.</span></span> <span data-ttu-id="b14f2-141">I diritti definiti da WCF sono definiti nella <xref:System.IdentityModel.Claims.Rights> classe.</span><span class="sxs-lookup"><span data-stu-id="b14f2-141">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="b14f2-142">È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il diritto sia univoco.</span><span class="sxs-lookup"><span data-stu-id="b14f2-142">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="b14f2-143">Nell'esempio di codice seguente viene creata un'attestazione personalizzata con un tipo di attestazione `http://example.org/claims/complexcustomclaim`, per un tipo di risorse personalizzato `MyResourceType`, e con il diritto <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="b14f2-143">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)]
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]
  
## <a name="example"></a><span data-ttu-id="b14f2-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="b14f2-144">Example</span></span>  
 <span data-ttu-id="b14f2-145">Nell'esempio di codice seguente viene illustrato come creare un'attestazione personalizzata con un tipo di risorsa primitivo e un'attestazione personalizzata con un tipo di risorsa non primitivo.</span><span class="sxs-lookup"><span data-stu-id="b14f2-145">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="b14f2-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b14f2-146">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="b14f2-147">Gestione di attestazioni e autorizzazioni con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="b14f2-147">Managing Claims and Authorization with the Identity Model</span></span>](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
