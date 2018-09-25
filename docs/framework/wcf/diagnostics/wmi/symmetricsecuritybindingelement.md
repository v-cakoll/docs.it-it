---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: 180b64f6f37e5c765585e52b292319816618be28
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076522"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="26275-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="26275-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="26275-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="26275-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26275-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26275-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="26275-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="26275-105">Methods</span></span>  
 <span data-ttu-id="26275-106">La classe SymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="26275-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="26275-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="26275-107">Properties</span></span>  
 <span data-ttu-id="26275-108">La classe SymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="26275-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="26275-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="26275-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="26275-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="26275-110">Data type: string</span></span>  
  
 <span data-ttu-id="26275-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="26275-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26275-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="26275-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="26275-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="26275-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="26275-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="26275-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="26275-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="26275-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="26275-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="26275-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26275-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26275-117">Requirements</span></span>  
  
|<span data-ttu-id="26275-118">MOF</span><span class="sxs-lookup"><span data-stu-id="26275-118">MOF</span></span>|<span data-ttu-id="26275-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="26275-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="26275-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="26275-120">Namespace</span></span>|<span data-ttu-id="26275-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="26275-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26275-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26275-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
