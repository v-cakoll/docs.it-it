---
title: MustUnderstandBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 40075acb2a098c98b4cd0ab35f213981c09f8486
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="29268-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="29268-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="29268-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="29268-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29268-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29268-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="29268-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="29268-105">Methods</span></span>  
 <span data-ttu-id="29268-106">La classe MustUnderstandBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="29268-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="29268-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="29268-107">Properties</span></span>  
 <span data-ttu-id="29268-108">La classe MustUnderstandBehavior dispone della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="29268-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="29268-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="29268-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="29268-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="29268-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="29268-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="29268-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="29268-112">Se `true`, tutte le intestazioni SOAP con l'attributo `MustUnderstand` non gestite determinano la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="29268-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29268-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29268-113">Requirements</span></span>  
  
|<span data-ttu-id="29268-114">MOF</span><span class="sxs-lookup"><span data-stu-id="29268-114">MOF</span></span>|<span data-ttu-id="29268-115">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="29268-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="29268-116">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="29268-116">Namespace</span></span>|<span data-ttu-id="29268-117">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="29268-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29268-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29268-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
