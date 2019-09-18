---
title: <Directives>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ec9a09e2fc03adbfcff0d7e69489e37da6e4a5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049877"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="e7c00-102">\<Elemento > delle direttive (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="e7c00-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="e7c00-103">Elemento radice in ogni file di direttive di runtime per .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e7c00-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="e7c00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7c00-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="e7c00-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="e7c00-105">Attributes</span></span>  
  
|<span data-ttu-id="e7c00-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="e7c00-106">Attribute</span></span>|<span data-ttu-id="e7c00-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7c00-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="e7c00-108">Spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="e7c00-108">The XML namespace.</span></span> <span data-ttu-id="e7c00-109">Il valore è sempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .</span><span class="sxs-lookup"><span data-stu-id="e7c00-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="e7c00-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e7c00-110">Child elements</span></span>  
  
|<span data-ttu-id="e7c00-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7c00-111">Element</span></span>|<span data-ttu-id="e7c00-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7c00-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7c00-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="e7c00-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="e7c00-114">Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection.</span><span class="sxs-lookup"><span data-stu-id="e7c00-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="e7c00-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="e7c00-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="e7c00-116">Definisce l'assembly i cui tipi di figlio e i membri di tipo richiedono metadati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e7c00-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7c00-117">Note</span><span class="sxs-lookup"><span data-stu-id="e7c00-117">Remarks</span></span>  
 <span data-ttu-id="e7c00-118">Ogni file di direttive di runtime può contenere un solo elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="e7c00-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="e7c00-119">L'elemento `<Directives>` può contenere zero o un elemento [\<Application>](application-element-net-native.md) e zero, uno o più elementi [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="e7c00-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c00-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7c00-120">See also</span></span>

- [<span data-ttu-id="e7c00-121">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="e7c00-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="e7c00-122">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="e7c00-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
