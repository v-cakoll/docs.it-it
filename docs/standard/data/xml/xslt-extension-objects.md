---
title: Oggetti di estensione XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
ms.openlocfilehash: 03e24153cc11c139fc9d9e692ef93bd82c51ee3d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282597"
---
# <a name="xslt-extension-objects"></a><span data-ttu-id="baa10-102">Oggetti di estensione XSLT</span><span class="sxs-lookup"><span data-stu-id="baa10-102">XSLT Extension Objects</span></span>
<span data-ttu-id="baa10-103">Gli oggetti di estensione vengono usati per estendere la funzionalità dei fogli di stile.</span><span class="sxs-lookup"><span data-stu-id="baa10-103">Extension objects are used to extend the functionality of style sheets.</span></span> <span data-ttu-id="baa10-104">Gli oggetti di estensione sono gestiti dalla classe <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="baa10-104">Extension objects are maintained by the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span>  
  
 <span data-ttu-id="baa10-105">Di seguito sono riportati i vantaggi derivanti dall'utilizzo di un oggetto di estensione anziché di uno script incorporato:</span><span class="sxs-lookup"><span data-stu-id="baa10-105">The following are advantages to using an extension object rather than embedded script:</span></span>  
  
- <span data-ttu-id="baa10-106">Migliore incapsulamento e riutilizzo delle classi.</span><span class="sxs-lookup"><span data-stu-id="baa10-106">Provides better encapsulation and reuse of classes.</span></span>  
  
- <span data-ttu-id="baa10-107">Fogli di stile di dimensioni minori e più gestibili.</span><span class="sxs-lookup"><span data-stu-id="baa10-107">Allows style sheets to be smaller and more maintainable.</span></span>  
  
 <span data-ttu-id="baa10-108">Gli oggetti di estensione XSLT vengono aggiunti all'oggetto <xref:System.Xml.Xsl.XsltArgumentList> usando il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="baa10-108">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> object using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="baa10-109">Un nome completo e un URI dello spazio dei nomi sono associati all'oggetto di estensione in quel momento.</span><span class="sxs-lookup"><span data-stu-id="baa10-109">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baa10-110">È richiesto il set di autorizzazioni FullTrust per chiamare il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="baa10-110">The FullTrust permission set is required to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="baa10-111">Per altre informazioni, vedere [Protezione dall'accesso di codice](../../../framework/misc/code-access-security.md) e [Set di autorizzazioni denominati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="baa10-111">For more information, see [Code Access Security](../../../framework/misc/code-access-security.md) and [Named Permission Sets](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span></span>  
  
 <span data-ttu-id="baa10-112">Dagli oggetti di estensione vengono restituiti dati appartenenti a uno dei quattro tipi di dati XPath principali, ovvero `number`, `string`, `Boolean` e `node set`.</span><span class="sxs-lookup"><span data-stu-id="baa10-112">The data types returned from extension objects are one of the four basic XPath data types of `number`, `string`, `Boolean`, and `node set`.</span></span>  
  
 <span data-ttu-id="baa10-113">I metodi definiti con la parola chiave `params`, che consente di passare un numero non specificato di parametri, non sono supportati dalla classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="baa10-113">Any method that is defined with the `params` keyword, which allows an unspecified number of parameters to be passed, is not currently supported by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="baa10-114">I fogli di stile XSLT in cui sono usati metodi definiti con la parola chiave `params` non funzioneranno correttamente.</span><span class="sxs-lookup"><span data-stu-id="baa10-114">XSLT style sheets that utilize any method defined with the `params` keyword will not work correctly.</span></span> <span data-ttu-id="baa10-115">Per informazioni dettagliate, vedere la sezione [params](../../../csharp/language-reference/keywords/params.md).</span><span class="sxs-lookup"><span data-stu-id="baa10-115">For details, see [params](../../../csharp/language-reference/keywords/params.md).</span></span>  
  
### <a name="to-use-an-xslt-extension-object"></a><span data-ttu-id="baa10-116">Per usare un oggetto di estensione XSLT</span><span class="sxs-lookup"><span data-stu-id="baa10-116">To use an XSLT extension object</span></span>  
  
1. <span data-ttu-id="baa10-117">Creare un tipo <xref:System.Xml.Xsl.XsltArgumentList> e aggiungere l'oggetto di estensione usando il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="baa10-117">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span>  
  
2. <span data-ttu-id="baa10-118">Chiamare l'oggetto di estensione dal foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="baa10-118">Call the extension object from the style sheet.</span></span>  
  
3. <span data-ttu-id="baa10-119">Passare l'oggetto <xref:System.Xml.Xsl.XsltArgumentList> al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="baa10-119">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa10-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baa10-120">See also</span></span>

- [<span data-ttu-id="baa10-121">Trasformazioni XSLT</span><span class="sxs-lookup"><span data-stu-id="baa10-121">XSLT Transformations</span></span>](xslt-transformations.md)
- [<span data-ttu-id="baa10-122">Considerazioni sulla sicurezza XSLT</span><span class="sxs-lookup"><span data-stu-id="baa10-122">XSLT Security Considerations</span></span>](xslt-security-considerations.md)
