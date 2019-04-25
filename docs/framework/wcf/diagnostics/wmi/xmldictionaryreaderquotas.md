---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f1c12a0a60397a84d4e9ff0241c4182b4511af5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61858429"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="3f194-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3f194-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="3f194-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3f194-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f194-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f194-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="3f194-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3f194-105">Methods</span></span>  
 <span data-ttu-id="3f194-106">La classe XmlDictionaryReaderQuotas non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="3f194-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3f194-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3f194-107">Properties</span></span>  
 <span data-ttu-id="3f194-108">La classe XmlDictionaryReaderQuotas presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f194-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="3f194-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="3f194-109">MaxArrayLength</span></span>  
 <span data-ttu-id="3f194-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3f194-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="3f194-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3f194-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f194-112">Lunghezza massima consentita della matrice.</span><span class="sxs-lookup"><span data-stu-id="3f194-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="3f194-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="3f194-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="3f194-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3f194-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="3f194-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3f194-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f194-116">Byte massimi consentiti restituiti per ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="3f194-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="3f194-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="3f194-117">MaxDepth</span></span>  
 <span data-ttu-id="3f194-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3f194-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="3f194-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3f194-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f194-120">Profondità massima dei nodi annidati per ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="3f194-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="3f194-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="3f194-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="3f194-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3f194-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="3f194-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3f194-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f194-124">Caratteri massimi consentiti in un nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="3f194-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="3f194-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="3f194-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="3f194-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="3f194-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="3f194-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="3f194-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f194-128">Caratteri massimi consentiti nel contenuto di un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="3f194-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f194-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f194-129">Requirements</span></span>  
  
|<span data-ttu-id="3f194-130">MOF</span><span class="sxs-lookup"><span data-stu-id="3f194-130">MOF</span></span>|<span data-ttu-id="3f194-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3f194-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3f194-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3f194-132">Namespace</span></span>|<span data-ttu-id="3f194-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3f194-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f194-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f194-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
