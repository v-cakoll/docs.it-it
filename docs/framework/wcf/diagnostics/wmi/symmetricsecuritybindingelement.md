---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7fc720f4f0be25a0cec25d979942af8472efa4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485056"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="61a43-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="61a43-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="61a43-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="61a43-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a43-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61a43-104">Syntax</span></span>  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="61a43-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="61a43-105">Methods</span></span>  
 <span data-ttu-id="61a43-106">La classe SymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="61a43-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="61a43-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="61a43-107">Properties</span></span>  
 <span data-ttu-id="61a43-108">La classe SymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="61a43-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="61a43-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="61a43-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="61a43-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="61a43-110">Data type: string</span></span>  
  
 <span data-ttu-id="61a43-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="61a43-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61a43-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="61a43-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="61a43-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="61a43-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="61a43-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="61a43-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="61a43-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="61a43-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="61a43-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="61a43-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61a43-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61a43-117">Requirements</span></span>  
  
|<span data-ttu-id="61a43-118">MOF</span><span class="sxs-lookup"><span data-stu-id="61a43-118">MOF</span></span>|<span data-ttu-id="61a43-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="61a43-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="61a43-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="61a43-120">Namespace</span></span>|<span data-ttu-id="61a43-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="61a43-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61a43-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61a43-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
