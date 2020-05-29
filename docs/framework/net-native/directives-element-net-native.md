---
title: <Directives>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 0c6ebb8954e80f3f6dc6733f0e9d76094477689b
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202375"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="62f1f-102">\<Directives>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="62f1f-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="62f1f-103">Elemento radice in ogni file di direttive di runtime per .NET Native.</span><span class="sxs-lookup"><span data-stu-id="62f1f-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="62f1f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62f1f-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="62f1f-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="62f1f-105">Attributes</span></span>  
  
|<span data-ttu-id="62f1f-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="62f1f-106">Attribute</span></span>|<span data-ttu-id="62f1f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62f1f-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="62f1f-108">Spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="62f1f-108">The XML namespace.</span></span> <span data-ttu-id="62f1f-109">Il valore è sempre `http://schemas.microsoft.com/netfx/2013/01/metadata` .</span><span class="sxs-lookup"><span data-stu-id="62f1f-109">Its value is always `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="62f1f-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="62f1f-110">Child elements</span></span>  
  
|<span data-ttu-id="62f1f-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="62f1f-111">Element</span></span>|<span data-ttu-id="62f1f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62f1f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="62f1f-113">Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection.</span><span class="sxs-lookup"><span data-stu-id="62f1f-113">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="62f1f-114">Definisce l'assembly i cui tipi di figlio e i membri di tipo richiedono metadati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="62f1f-114">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62f1f-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="62f1f-115">Remarks</span></span>  
 <span data-ttu-id="62f1f-116">Ogni file di direttive di runtime può contenere un solo elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="62f1f-116">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="62f1f-117">L' `<Directives>` elemento può contenere zero o un [\<Application>](application-element-net-native.md) elemento e zero, uno o più [\<Library>](library-element-net-native.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="62f1f-117">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f1f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62f1f-118">See also</span></span>

- [<span data-ttu-id="62f1f-119">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="62f1f-119">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="62f1f-120">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="62f1f-120">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
