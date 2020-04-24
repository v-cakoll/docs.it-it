---
title: Spazi dei nomi e DTD nel DOM (Document Object Model)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1e9b55c4-76ad-4f54-8d96-7ce4b4cf1e05
ms.openlocfilehash: 22762e3a7003d9b28a53c7b500829aaa41924c6d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710596"
---
# <a name="namespaces-and-dtds-in-the-dom"></a><span data-ttu-id="b6e84-102">Spazi dei nomi e DTD nel DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="b6e84-102">Namespaces and DTDs in the DOM</span></span>
<span data-ttu-id="b6e84-103">Le DTD (Document Type Definition) rendono più complicato il supporto dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b6e84-103">Document type definitions (DTDs) complicate namespace support.</span></span> <span data-ttu-id="b6e84-104">Ad esempio, nel seguente codice XML sono presenti attributi predefiniti contenenti due punti nei nomi.</span><span class="sxs-lookup"><span data-stu-id="b6e84-104">For example, the following XML contains default attributes containing colons in their names.</span></span>  
  
```xml  
<!ATTLIST item x:id CDATA #IMPLIED>  
```  
  
 <span data-ttu-id="b6e84-105">Di seguito sono riportate le possibili risoluzioni se il costrutto è consentito:</span><span class="sxs-lookup"><span data-stu-id="b6e84-105">The following are possible resolutions if this construct is allowed:</span></span>  
  
- <span data-ttu-id="b6e84-106">Il codice `x:` viene considerato come prefisso dello spazio dei nomi, ma il prefisso deve essere risolvibile usando una dichiarazione dello spazio dei nomi `xmlns:x`, che deve inoltre essere presente nella DTD.</span><span class="sxs-lookup"><span data-stu-id="b6e84-106">The `x:` is treated as a namespace prefix, but this prefix must be resolvable using an `xmlns:x` namespace declaration, which must also exist somewhere in the DTD.</span></span> <span data-ttu-id="b6e84-107">Il mapping di questo prefisso non deve essere eseguito a un elemento diverso nel documento dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b6e84-107">It is an error to map this prefix to something different in the instance document.</span></span>  
  
- <span data-ttu-id="b6e84-108">Il codice `x:` viene considerato come prefisso dello spazio dei nomi, ma tale prefisso è sempre risolto nel contesto degli elementi dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b6e84-108">The `x:` is treated as a namespace prefix, but this prefix is always resolved in the context of the instance elements.</span></span> <span data-ttu-id="b6e84-109">È pertanto possibile eseguire il mapping del prefisso a URI (Uniform Resource Identifier) diversi dello spazio dei nomi, in base all'ambito dello spazio dei nomi in cui è presente l'elemento `item`.</span><span class="sxs-lookup"><span data-stu-id="b6e84-109">This means the prefix could actually map to different namespace Uniform Resource Identifiers (URIs), depending on the namespace scope in which the `item` element appears.</span></span> <span data-ttu-id="b6e84-110">Questo comportamento è più prevedibile rispetto alla risoluzione fornita nel punto elenco precedente, ma presenta altre implicazioni complesse poiché richiede che gli attributi predefiniti vengano materializzati.</span><span class="sxs-lookup"><span data-stu-id="b6e84-110">This behavior is more predictable than the resolution given in the earlier bullet, but it has other complicated ramifications because it requires the default attributes be materialized.</span></span>  
  
- <span data-ttu-id="b6e84-111">I due punti vengono ignorati in quanto si trovano in una DTD e il nome dell'attributo è `x:y`, senza prefisso e URI dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b6e84-111">The colon is ignored because it is in a DTD, and the name of the attribute is `x:y`, no prefix and no namespace URI.</span></span>  
  
- <span data-ttu-id="b6e84-112">I due punti nell'attributo predefinito generano un'eccezione, per indicare che i due punti nei nomi all'interno di una DTD non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b6e84-112">The colon in the default attribute throws an exception, saying that colons in names inside a DTD are not supported.</span></span> <span data-ttu-id="b6e84-113">Il comportamento è prevedibile, ma implica che non sarà possibile caricare molte delle DTD pubblicate dal W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="b6e84-113">This results in a predictable behavior, but means you cannot load many of the World Wide Web Consortium (W3C) published DTDs.</span></span>  
  
- <span data-ttu-id="b6e84-114">Quando l'utente richiede la convalida della DTD, il supporto per lo spazio dei nomi viene disattivato per l'intero documento.</span><span class="sxs-lookup"><span data-stu-id="b6e84-114">When the user requests DTD validation, namespace support for the entire document is turned off.</span></span> <span data-ttu-id="b6e84-115">In tal modo è possibile caricare le DTD W3C e ottenere un comportamento prevedibile.</span><span class="sxs-lookup"><span data-stu-id="b6e84-115">This makes it possible to load W3C DTDs and results in a predictable behavior.</span></span>  
  
 <span data-ttu-id="b6e84-116">Il codice XML in Microsoft .NET Framework implementa la seconda opzione per garantire la massima compatibilità con le specifiche W3C.</span><span class="sxs-lookup"><span data-stu-id="b6e84-116">The XML in the Microsoft .NET Framework implements the second option for maximum W3C compatibility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e84-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b6e84-117">See also</span></span>

- [<span data-ttu-id="b6e84-118">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="b6e84-118">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
