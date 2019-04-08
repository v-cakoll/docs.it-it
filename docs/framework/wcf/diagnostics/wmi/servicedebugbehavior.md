---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090914"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="bcfce-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="bcfce-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="bcfce-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="bcfce-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcfce-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bcfce-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="bcfce-105">Methods</span></span>  
 <span data-ttu-id="bcfce-106">La classe ServiceDebugBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="bcfce-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bcfce-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="bcfce-107">Properties</span></span>  
 <span data-ttu-id="bcfce-108">La classe ServiceDebugBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcfce-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="bcfce-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="bcfce-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="bcfce-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="bcfce-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="bcfce-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="bcfce-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcfce-112">Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="bcfce-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="bcfce-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="bcfce-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="bcfce-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="bcfce-114">Data type: string</span></span>  
  
 <span data-ttu-id="bcfce-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="bcfce-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcfce-116">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="bcfce-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="bcfce-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="bcfce-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="bcfce-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="bcfce-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="bcfce-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="bcfce-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcfce-120">Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="bcfce-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="bcfce-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="bcfce-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="bcfce-122">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="bcfce-122">Data type: string</span></span>  
  
 <span data-ttu-id="bcfce-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="bcfce-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcfce-124">Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bcfce-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="bcfce-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="bcfce-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="bcfce-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="bcfce-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="bcfce-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="bcfce-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcfce-128">Specifica se includere informazioni di eccezione nei dettagli degli errori SOAP restituiti ai client a fini di debug.</span><span class="sxs-lookup"><span data-stu-id="bcfce-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcfce-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcfce-129">Requirements</span></span>  
  
|<span data-ttu-id="bcfce-130">MOF</span><span class="sxs-lookup"><span data-stu-id="bcfce-130">MOF</span></span>|<span data-ttu-id="bcfce-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bcfce-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bcfce-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="bcfce-132">Namespace</span></span>|<span data-ttu-id="bcfce-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bcfce-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcfce-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcfce-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
