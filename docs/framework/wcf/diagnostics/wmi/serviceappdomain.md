---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485668"
---
# <a name="serviceappdomain"></a><span data-ttu-id="9a84a-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="9a84a-102">ServiceAppDomain</span></span>
<span data-ttu-id="9a84a-103">Esegue il mapping di un servizio a un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a84a-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a84a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a84a-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9a84a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9a84a-105">Methods</span></span>  
 <span data-ttu-id="9a84a-106">La classe ServiceAppDomain non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="9a84a-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9a84a-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9a84a-107">Properties</span></span>  
 <span data-ttu-id="9a84a-108">La classe ServiceAppDomain presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a84a-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9a84a-109">ref</span><span class="sxs-lookup"><span data-stu-id="9a84a-109">ref</span></span>  
 <span data-ttu-id="9a84a-110">Tipo di dati: servizio</span><span class="sxs-lookup"><span data-stu-id="9a84a-110">Data type: Service</span></span>  
<span data-ttu-id="9a84a-111">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="9a84a-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="9a84a-112">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9a84a-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9a84a-113">Il servizio di questo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a84a-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9a84a-114">ref</span><span class="sxs-lookup"><span data-stu-id="9a84a-114">ref</span></span>  
 <span data-ttu-id="9a84a-115">Tipo di dati: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="9a84a-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="9a84a-116">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="9a84a-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="9a84a-117">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="9a84a-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9a84a-118">Contiene proprietà del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a84a-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a84a-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a84a-119">Requirements</span></span>  
  
|<span data-ttu-id="9a84a-120">MOF</span><span class="sxs-lookup"><span data-stu-id="9a84a-120">MOF</span></span>|<span data-ttu-id="9a84a-121">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9a84a-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9a84a-122">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="9a84a-122">Namespace</span></span>|<span data-ttu-id="9a84a-123">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9a84a-123">Defined in root\ServiceModel</span></span>|
