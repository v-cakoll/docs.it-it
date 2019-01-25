---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f24865fb0affa7b4516a14fc05b905995826e82e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597671"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="27f0c-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="27f0c-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="27f0c-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="27f0c-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27f0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27f0c-104">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="27f0c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="27f0c-105">Methods</span></span>  
 <span data-ttu-id="27f0c-106">La classe XmlDictionaryReaderQuotas non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="27f0c-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="27f0c-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="27f0c-107">Properties</span></span>  
 <span data-ttu-id="27f0c-108">La classe XmlDictionaryReaderQuotas presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="27f0c-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="27f0c-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="27f0c-109">MaxArrayLength</span></span>  
 <span data-ttu-id="27f0c-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="27f0c-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="27f0c-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="27f0c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27f0c-112">Lunghezza massima consentita della matrice.</span><span class="sxs-lookup"><span data-stu-id="27f0c-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="27f0c-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="27f0c-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="27f0c-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="27f0c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="27f0c-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="27f0c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27f0c-116">Byte massimi consentiti restituiti per ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="27f0c-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="27f0c-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="27f0c-117">MaxDepth</span></span>  
 <span data-ttu-id="27f0c-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="27f0c-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="27f0c-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="27f0c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27f0c-120">Profondità massima dei nodi annidati per ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="27f0c-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="27f0c-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="27f0c-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="27f0c-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="27f0c-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="27f0c-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="27f0c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27f0c-124">Caratteri massimi consentiti in un nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="27f0c-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="27f0c-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="27f0c-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="27f0c-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="27f0c-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="27f0c-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="27f0c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27f0c-128">Caratteri massimi consentiti nel contenuto di un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="27f0c-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27f0c-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27f0c-129">Requirements</span></span>  
  
|<span data-ttu-id="27f0c-130">MOF</span><span class="sxs-lookup"><span data-stu-id="27f0c-130">MOF</span></span>|<span data-ttu-id="27f0c-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="27f0c-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="27f0c-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="27f0c-132">Namespace</span></span>|<span data-ttu-id="27f0c-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="27f0c-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27f0c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27f0c-134">See also</span></span>
- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
