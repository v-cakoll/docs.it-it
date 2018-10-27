---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192239"
---
# <a name="serviceappdomain"></a><span data-ttu-id="94da5-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="94da5-102">ServiceAppDomain</span></span>
<span data-ttu-id="94da5-103">Esegue il mapping di un servizio a un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="94da5-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94da5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94da5-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="94da5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="94da5-105">Methods</span></span>  
 <span data-ttu-id="94da5-106">La classe ServiceAppDomain non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="94da5-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="94da5-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="94da5-107">Properties</span></span>  
 <span data-ttu-id="94da5-108">La classe ServiceAppDomain presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="94da5-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="94da5-109">ref</span><span class="sxs-lookup"><span data-stu-id="94da5-109">ref</span></span>  
 <span data-ttu-id="94da5-110">Tipo di dati: servizio</span><span class="sxs-lookup"><span data-stu-id="94da5-110">Data type: Service</span></span>  
<span data-ttu-id="94da5-111">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="94da5-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="94da5-112">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="94da5-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94da5-113">Il servizio di questo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="94da5-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="94da5-114">ref</span><span class="sxs-lookup"><span data-stu-id="94da5-114">ref</span></span>  
 <span data-ttu-id="94da5-115">Tipo di dati: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="94da5-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="94da5-116">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="94da5-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="94da5-117">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="94da5-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94da5-118">Contiene proprietà del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="94da5-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94da5-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94da5-119">Requirements</span></span>  
  
|<span data-ttu-id="94da5-120">MOF</span><span class="sxs-lookup"><span data-stu-id="94da5-120">MOF</span></span>|<span data-ttu-id="94da5-121">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="94da5-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="94da5-122">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="94da5-122">Namespace</span></span>|<span data-ttu-id="94da5-123">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="94da5-123">Defined in root\ServiceModel</span></span>|
