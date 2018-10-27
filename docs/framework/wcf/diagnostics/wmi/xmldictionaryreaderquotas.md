---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044229"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="2e828-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="2e828-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="2e828-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="2e828-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e828-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e828-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="2e828-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="2e828-105">Methods</span></span>  
 <span data-ttu-id="2e828-106">La classe XmlDictionaryReaderQuotas non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="2e828-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2e828-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2e828-107">Properties</span></span>  
 <span data-ttu-id="2e828-108">La classe XmlDictionaryReaderQuotas presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e828-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="2e828-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="2e828-109">MaxArrayLength</span></span>  
 <span data-ttu-id="2e828-110">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="2e828-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e828-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="2e828-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e828-112">Lunghezza massima consentita della matrice.</span><span class="sxs-lookup"><span data-stu-id="2e828-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="2e828-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="2e828-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="2e828-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="2e828-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e828-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="2e828-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e828-116">Byte massimi consentiti restituiti per ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="2e828-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="2e828-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="2e828-117">MaxDepth</span></span>  
 <span data-ttu-id="2e828-118">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="2e828-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e828-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="2e828-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e828-120">Profondità massima dei nodi annidati per ogni lettura.</span><span class="sxs-lookup"><span data-stu-id="2e828-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="2e828-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="2e828-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="2e828-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="2e828-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e828-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="2e828-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e828-124">Caratteri massimi consentiti in un nome di tabella.</span><span class="sxs-lookup"><span data-stu-id="2e828-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="2e828-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="2e828-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="2e828-126">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="2e828-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e828-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="2e828-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e828-128">Caratteri massimi consentiti nel contenuto di un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="2e828-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e828-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e828-129">Requirements</span></span>  
  
|<span data-ttu-id="2e828-130">MOF</span><span class="sxs-lookup"><span data-stu-id="2e828-130">MOF</span></span>|<span data-ttu-id="2e828-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2e828-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2e828-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="2e828-132">Namespace</span></span>|<span data-ttu-id="2e828-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2e828-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e828-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e828-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
