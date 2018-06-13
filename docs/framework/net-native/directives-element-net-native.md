---
title: Elemento &lt;Directives&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd571255f924c9f3878c00a2bc01397d63e6d777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394446"
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="e8237-102">Elemento &lt;Directives&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="e8237-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="e8237-103">Elemento radice in ogni file di direttive di runtime per [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8237-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="e8237-104">**\<Direttive xmlns = "http://schemas.microsoft.com/netfx/2013/01/metadata" >**</span><span class="sxs-lookup"><span data-stu-id="e8237-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8237-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8237-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="e8237-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8237-106">Attributes</span></span>  
  
|<span data-ttu-id="e8237-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="e8237-107">Attribute</span></span>|<span data-ttu-id="e8237-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8237-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="e8237-109">Spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="e8237-109">The XML namespace.</span></span> <span data-ttu-id="e8237-110">Il valore è sempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="e8237-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="e8237-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8237-111">Child elements</span></span>  
  
|<span data-ttu-id="e8237-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8237-112">Element</span></span>|<span data-ttu-id="e8237-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8237-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8237-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="e8237-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="e8237-115">Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection.</span><span class="sxs-lookup"><span data-stu-id="e8237-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="e8237-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="e8237-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="e8237-117">Definisce l'assembly i cui tipi di figlio e i membri di tipo richiedono metadati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e8237-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8237-118">Note</span><span class="sxs-lookup"><span data-stu-id="e8237-118">Remarks</span></span>  
 <span data-ttu-id="e8237-119">Ogni file di direttive di runtime può contenere un solo elemento `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="e8237-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="e8237-120">L'elemento `<Directives>` può contenere zero o un elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) e zero, uno o più elementi [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="e8237-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8237-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8237-121">See Also</span></span>  
 [<span data-ttu-id="e8237-122">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="e8237-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="e8237-123">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="e8237-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
