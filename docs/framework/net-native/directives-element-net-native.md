---
title: <Directives>Elemento (.NET native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181051"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="2c311-102">\<Direttive>elemento (.NET native)Directives (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="2c311-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="2c311-103">Elemento radice in ogni file di direttive di runtime per .NET Native.The root element in every runtime directives file for .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2c311-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="2c311-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c311-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="2c311-105">Attributes</span><span class="sxs-lookup"><span data-stu-id="2c311-105">Attributes</span></span>  
  
|<span data-ttu-id="2c311-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="2c311-106">Attribute</span></span>|<span data-ttu-id="2c311-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c311-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="2c311-108">Spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="2c311-108">The XML namespace.</span></span> <span data-ttu-id="2c311-109">Il suo valore è sempre **"http://schemas.microsoft.com/netfx/2013/01/metadata" .**</span><span class="sxs-lookup"><span data-stu-id="2c311-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="2c311-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2c311-110">Child elements</span></span>  
  
|<span data-ttu-id="2c311-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c311-111">Element</span></span>|<span data-ttu-id="2c311-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c311-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c311-113">\<>dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="2c311-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="2c311-114">Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection.</span><span class="sxs-lookup"><span data-stu-id="2c311-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="2c311-115">\<>libreria</span><span class="sxs-lookup"><span data-stu-id="2c311-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="2c311-116">Definisce l'assembly i cui tipi di figlio e i membri di tipo richiedono metadati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2c311-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c311-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2c311-117">Remarks</span></span>  
 <span data-ttu-id="2c311-118">Ogni file di direttive di runtime può contenere un solo elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="2c311-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="2c311-119">L'elemento `<Directives>` può contenere zero o un [ \<elemento Application>](application-element-net-native.md) e zero, uno o più [ \<](library-element-net-native.md) elementi Library>.</span><span class="sxs-lookup"><span data-stu-id="2c311-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c311-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c311-120">See also</span></span>

- [<span data-ttu-id="2c311-121">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="2c311-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="2c311-122">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="2c311-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
