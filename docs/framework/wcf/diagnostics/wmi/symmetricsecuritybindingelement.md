---
title: SymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ab341f55947bfcfbc776143e3bbc33e125da89c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="fd3e0-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="fd3e0-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="fd3e0-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="fd3e0-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd3e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd3e0-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fd3e0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fd3e0-105">Methods</span></span>  
 <span data-ttu-id="fd3e0-106">La classe SymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fd3e0-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fd3e0-107">Properties</span></span>  
 <span data-ttu-id="fd3e0-108">La classe SymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="fd3e0-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="fd3e0-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="fd3e0-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="fd3e0-110">Data type: string</span></span>  
  
 <span data-ttu-id="fd3e0-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fd3e0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd3e0-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="fd3e0-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="fd3e0-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="fd3e0-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="fd3e0-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="fd3e0-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fd3e0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd3e0-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd3e0-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd3e0-117">Requirements</span></span>  
  
|<span data-ttu-id="fd3e0-118">MOF</span><span class="sxs-lookup"><span data-stu-id="fd3e0-118">MOF</span></span>|<span data-ttu-id="fd3e0-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fd3e0-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="fd3e0-120">Namespace</span></span>|<span data-ttu-id="fd3e0-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fd3e0-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd3e0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd3e0-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
