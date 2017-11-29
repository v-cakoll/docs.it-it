---
title: ServiceTimeoutsBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4b597dbdd8dfea1cab35c717f416d91677c5987
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="f7536-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="f7536-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="f7536-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="f7536-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7536-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7536-104">Syntax</span></span>  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f7536-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f7536-105">Methods</span></span>  
 <span data-ttu-id="f7536-106">La classe ServiceTimeoutsBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="f7536-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f7536-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f7536-107">Properties</span></span>  
 <span data-ttu-id="f7536-108">La classe ServiceTimeoutsBehavior dispone della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="f7536-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="f7536-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="f7536-109">TransactionTimeout</span></span>  
 <span data-ttu-id="f7536-110">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="f7536-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="f7536-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="f7536-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7536-112">Periodo entro il quale una transazione deve essere completata.</span><span class="sxs-lookup"><span data-stu-id="f7536-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7536-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7536-113">Requirements</span></span>  
  
|<span data-ttu-id="f7536-114">MOF</span><span class="sxs-lookup"><span data-stu-id="f7536-114">MOF</span></span>|<span data-ttu-id="f7536-115">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f7536-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f7536-116">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="f7536-116">Namespace</span></span>|<span data-ttu-id="f7536-117">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f7536-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7536-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7536-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
