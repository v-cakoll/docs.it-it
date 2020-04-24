---
title: Navigazione dello spazio dei nomi XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 06cc7abb-7416-415c-9dd6-67751b8cabd5
ms.openlocfilehash: f35318b1439b762bf7c87cff217ed1787e8d007c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156322"
---
# <a name="xpath-namespace-navigation"></a><span data-ttu-id="63169-102">Navigazione dello spazio dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="63169-102">XPath Namespace Navigation</span></span>
<span data-ttu-id="63169-103">Per usare le query XPath con i documenti XML, è necessario indirizzare correttamente gli spazi dei nomi XML e gli elementi da questi contenuti.</span><span class="sxs-lookup"><span data-stu-id="63169-103">To use XPath queries with XML documents, you have to correctly address XML namespaces and the elements contained by namespaces.</span></span> <span data-ttu-id="63169-104">Gli spazi dei nomi evitano le ambiguità che si possono verificare quando i nomi vengono usati in più contesti; ad esempio il nome `ID` potrebbe far riferimento a più identificatori associati a diversi elementi di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="63169-104">Namespaces prevent ambiguities that can occur when names are used in more than one context; for example, the name `ID` may refer to more than one identifier associated with different elements of an XML document.</span></span> <span data-ttu-id="63169-105">La sintassi dello spazio dei nomi specifica gli URI, i nomi e i prefissi che distinguono gli elementi di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="63169-105">Namespace syntax specifies URIs, names, and prefixes that distinguish the elements of an XML document.</span></span>  
  
 <span data-ttu-id="63169-106">Nell'esempio di questo argomento viene illustrato l'uso di prefissi nella navigazione di un documento XML con l'oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="63169-106">The example in this topic demonstrates the use of prefixes in navigating an XML document with <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="63169-107">Per ulteriori informazioni sugli spazi dei nomi e sulla sintassi, vedere [file XML: informazioni sugli spazi dei nomi XML](https://docs.microsoft.com/previous-versions/dotnet/articles/bb986013(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="63169-107">For more information about namespaces and syntax, see [XML Files: Understanding XML Namespaces](https://docs.microsoft.com/previous-versions/dotnet/articles/bb986013(v=msdn.10)).</span></span>  
  
## <a name="namespace-declarations"></a><span data-ttu-id="63169-108">Dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="63169-108">Namespace Declarations</span></span>  
 <span data-ttu-id="63169-109">Le dichiarazioni dello spazio dei nomi consentono di distinguere e indirizzare gli elementi di un documento XML quando si usa un'istanza dell'oggetto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="63169-109">Namespace declarations make the elements of an XML document distinguishable and addressable when using an instance of <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="63169-110">I prefissi dello spazio dei nomi forniscono una breve sintassi per l'indirizzamento degli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="63169-110">Namespace prefixes provide a brief syntax for addressing namespaces.</span></span>  
  
 <span data-ttu-id="63169-111">I prefissi sono definiti dal formato: `<e:Envelope xmlns:e=http://schemas.xmlsoap.org/soap/envelope/>.` In questa sintassi il prefisso "`e`" è un'abbreviazione dell'URI formale dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="63169-111">Prefixes are defined by the form: `<e:Envelope xmlns:e=http://schemas.xmlsoap.org/soap/envelope/>.` In this syntax the prefix "`e`" is an abbreviation for the formal URI of the namespace.</span></span> <span data-ttu-id="63169-112">È possibile identificare l'elemento `Body` come membro dello spazio dei nomi `Envelope` tramite la sintassi: `e:Body`.</span><span class="sxs-lookup"><span data-stu-id="63169-112">You can identify the `Body` element as a member of the `Envelope` namespace by using the syntax: `e:Body`.</span></span>  
  
 <span data-ttu-id="63169-113">Nell'esempio di navigazione della sezione successiva, al seguente documento XML verrà fatto riferimento come `response.xml`.</span><span class="sxs-lookup"><span data-stu-id="63169-113">The following XML document will be referenced as `response.xml` in the navigation example in the next section.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<e:Envelope xmlns:e="http://schemas.xmlsoap.org/soap/envelope/">  
  <e:Body>  
    <s:Search xmlns:s="http://schemas.microsoft.com/v1/Search">  
      <r:request xmlns:r="http://schemas.microsoft.com/v1/Search/metadata"
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance">  
      </r:request>  
    </s:Search>  
  </e:Body>  
</e:Envelope>  
```  
  
## <a name="navigation-by-namespace-prefix"></a><span data-ttu-id="63169-114">Navigazione tramite il prefisso dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="63169-114">Navigation by Namespace Prefix</span></span>  
 <span data-ttu-id="63169-115">Nel codice di questa sezione vengono usati gli oggetti <xref:System.Xml.XPath.XPathNavigator> e <xref:System.Xml.XmlNamespaceManager> per selezionare l'elemento `Search` dal documento XML della sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="63169-115">The code in this section uses <xref:System.Xml.XPath.XPathNavigator> and <xref:System.Xml.XmlNamespaceManager> objects to select the `Search` element from the XML document in the previous section.</span></span> <span data-ttu-id="63169-116">La query `xpath` include i prefissi dello spazio dei nomi in ogni elemento del percorso.</span><span class="sxs-lookup"><span data-stu-id="63169-116">The query `xpath` includes namespace prefixes on each element in the path.</span></span> <span data-ttu-id="63169-117">Specificando l'esatta identità degli spazi dei nomi che contengono ogni elemento è possibile garantire la corretta navigazione all'elemento `Search` tramite il metodo <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>.</span><span class="sxs-lookup"><span data-stu-id="63169-117">Specifying the precise identity of the namespaces that contain each element assures correct navigation to the `Search` element by the <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> method.</span></span>  
  
```csharp  
using (XmlReader reader = XmlReader.Create("response.xml"))  
{  
    XPathDocument doc = new XPathDocument(reader);  
    XPathNavigator nav = doc.CreateNavigator();
  
    XmlNamespaceManager nsmgr = new XmlNamespaceManager(nav.NameTable);  
    nsmgr.AddNamespace("e", @"http://schemas.xmlsoap.org/soap/envelope/");  
    nsmgr.AddNamespace("s", @"http://schemas.microsoft.com/v1/Search");  
    nsmgr.AddNamespace("r", @"http://schemas.microsoft.com/v1/Search/metadata");  
    nsmgr.AddNamespace("i", @"http://www.w3.org/2001/XMLSchema-instance");  
  
    string xpath = "/e:Envelope/e:Body/s:Search";  
  
    XPathNavigator element = nav.SelectSingleNode(xpath, nsmgr);  
  
    Console.WriteLine("Element Prefix:" + element.Prefix +
    " Local name:" + element.LocalName);  
    Console.WriteLine("Namespace URI: " + element.NamespaceURI);  
}  
```  
  
 <span data-ttu-id="63169-118">La precisione assicurata dalla qualifica completa degli spazi dei nomi e dei nomi non è soltanto utile,</span><span class="sxs-lookup"><span data-stu-id="63169-118">The precision of fully qualifying namespaces and names is more than a convenience.</span></span> <span data-ttu-id="63169-119">infatti da un breve esperimento con la definizione di documento e il codice degli esempi precedenti è possibile constatare che la navigazione senza nomi di elementi completi genera eccezioni.</span><span class="sxs-lookup"><span data-stu-id="63169-119">A little experimentation with the document definition and code in the previous examples will verify that navigation without fully qualified element names throws exceptions.</span></span> <span data-ttu-id="63169-120">Ad esempio la definizione di elemento: `<Search xmlns="http://schemas.microsoft.com/v1/Search">` e la query: stringa `xpath = "/s:Envelope/s:Body/Search";` senza il prefisso dello spazio dei nomi nell'elemento `Search` restituisce `null` invece dell'elemento `Search`.</span><span class="sxs-lookup"><span data-stu-id="63169-120">For example, the element definition: `<Search xmlns="http://schemas.microsoft.com/v1/Search">`, and query: string `xpath = "/s:Envelope/s:Body/Search";` without the namespace prefix on the `Search` element returns `null` instead of the `Search` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63169-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="63169-121">See also</span></span>

- [<span data-ttu-id="63169-122">Accesso ai dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="63169-122">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="63169-123">Selezione, valutazione e corrispondenza di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="63169-123">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
