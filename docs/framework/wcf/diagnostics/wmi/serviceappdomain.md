---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2018
ms.locfileid: "49479524"
---
# <a name="serviceappdomain"></a><span data-ttu-id="797a6-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="797a6-102">ServiceAppDomain</span></span>
<span data-ttu-id="797a6-103">Esegue il mapping di un servizio a un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="797a6-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="797a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="797a6-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="797a6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="797a6-105">Methods</span></span>  
 <span data-ttu-id="797a6-106">La classe ServiceAppDomain non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="797a6-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="797a6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="797a6-107">Properties</span></span>  
 <span data-ttu-id="797a6-108">La classe ServiceAppDomain presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="797a6-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="797a6-109">ref</span><span class="sxs-lookup"><span data-stu-id="797a6-109">ref</span></span>  
 <span data-ttu-id="797a6-110">Tipo di dati: servizio</span><span class="sxs-lookup"><span data-stu-id="797a6-110">Data type: Service</span></span>  
<span data-ttu-id="797a6-111">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="797a6-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="797a6-112">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="797a6-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="797a6-113">Il servizio di questo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="797a6-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="797a6-114">ref</span><span class="sxs-lookup"><span data-stu-id="797a6-114">ref</span></span>  
 <span data-ttu-id="797a6-115">Tipo di dati: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="797a6-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="797a6-116">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="797a6-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="797a6-117">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="797a6-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="797a6-118">Contiene proprietà del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="797a6-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="797a6-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="797a6-119">Requirements</span></span>  
  
|<span data-ttu-id="797a6-120">MOF</span><span class="sxs-lookup"><span data-stu-id="797a6-120">MOF</span></span>|<span data-ttu-id="797a6-121">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="797a6-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="797a6-122">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="797a6-122">Namespace</span></span>|<span data-ttu-id="797a6-123">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="797a6-123">Defined in root\ServiceModel</span></span>|
