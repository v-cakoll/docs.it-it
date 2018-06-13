---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 76c4992c5364ed9800e58d120c099aceedb2799c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485681"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="fff6b-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="fff6b-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="fff6b-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="fff6b-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fff6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fff6b-104">Syntax</span></span>  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fff6b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fff6b-105">Methods</span></span>  
 <span data-ttu-id="fff6b-106">La classe ServiceDebugBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="fff6b-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fff6b-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fff6b-107">Properties</span></span>  
 <span data-ttu-id="fff6b-108">La classe ServiceDebugBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="fff6b-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="fff6b-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="fff6b-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="fff6b-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="fff6b-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="fff6b-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fff6b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fff6b-112">Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="fff6b-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="fff6b-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="fff6b-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="fff6b-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="fff6b-114">Data type: string</span></span>  
  
 <span data-ttu-id="fff6b-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fff6b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fff6b-116">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="fff6b-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="fff6b-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="fff6b-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="fff6b-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="fff6b-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="fff6b-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fff6b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fff6b-120">Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="fff6b-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="fff6b-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="fff6b-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="fff6b-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="fff6b-122">Data type: string</span></span>  
  
 <span data-ttu-id="fff6b-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fff6b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fff6b-124">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fff6b-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="fff6b-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="fff6b-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="fff6b-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="fff6b-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="fff6b-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="fff6b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fff6b-128">Specifica se includere informazioni di eccezione nei dettagli degli errori SOAP restituiti ai client a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="fff6b-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fff6b-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fff6b-129">Requirements</span></span>  
  
|<span data-ttu-id="fff6b-130">MOF</span><span class="sxs-lookup"><span data-stu-id="fff6b-130">MOF</span></span>|<span data-ttu-id="fff6b-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fff6b-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fff6b-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="fff6b-132">Namespace</span></span>|<span data-ttu-id="fff6b-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fff6b-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fff6b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fff6b-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
