---
title: Frammento di alberi risultato nelle trasformazioni
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
ms.openlocfilehash: e454c1194e8c280042857f106e22d0d0509417e3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156361"
---
# <a name="result-tree-fragment-in-transformations"></a><span data-ttu-id="17db0-102">Frammento di alberi risultato nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="17db0-102">Result Tree Fragment in Transformations</span></span>

> [!NOTE]
> <span data-ttu-id="17db0-103">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="17db0-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="17db0-104">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="17db0-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="17db0-105">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="17db0-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

 <span data-ttu-id="17db0-106">I frammenti di nodi, detti anche frammenti di albero risultato, sono semplicemente un particolare tipo di set di nodi.</span><span class="sxs-lookup"><span data-stu-id="17db0-106">Result tree fragments, also known as result tree fragments, are nothing more than a special type of node set.</span></span> <span data-ttu-id="17db0-107">Sui frammenti di nodi è possibile eseguire le stesse funzioni che sono eseguibili sui set di nodi.</span><span class="sxs-lookup"><span data-stu-id="17db0-107">You can perform any function on them that can be performed on a node set.</span></span> <span data-ttu-id="17db0-108">È inoltre possibile usare la funzione `node-set()` per convertire un frammento di albero risultato in un set di nodi, quindi usarlo in qualsiasi posizione adatta.</span><span class="sxs-lookup"><span data-stu-id="17db0-108">Or, you can also convert a result tree fragment to a node set using the `node-set()` function and subsequently use it any place that a node set can be used.</span></span>

 <span data-ttu-id="17db0-109">Un frammento di albero risultato viene creato usando in modo specifico un elemento `<xsl:variable>` o `<xsl:param>` in un foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="17db0-109">A result tree fragment is created as a result of using an `<xsl:variable>` or `<xsl:param>` element in a specific manner in a style sheet.</span></span> <span data-ttu-id="17db0-110">La sintassi degli elementi `variable` e `parameter` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="17db0-110">The syntax for the `variable` and `parameter` elements is as follows:</span></span>

```xml
<xsl:param name=Qname select= XPath Expression >
    template body
</xsl:param>

<xsl:variable name=Qname select=XPath Expression >
    template body
</xsl:variable>
```

<span data-ttu-id="17db0-111">Il valore del nome completo (`parameter`) dell'elemento `Qname` può essere assegnato in vari modi.</span><span class="sxs-lookup"><span data-stu-id="17db0-111">For the `parameter` element, the value is assigned to the qualified name (`Qname`) in several ways.</span></span> <span data-ttu-id="17db0-112">È possibile assegnare al parametro un valore predefinito tramite il contenuto restituito dall'espressione XPath nell'attributo `select` oppure usando il contenuto del corpo del modello.</span><span class="sxs-lookup"><span data-stu-id="17db0-112">You can assign a default value to the parameter by returning content from the XML Path Language (XPath) expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="17db0-113">Anche il valore dell'elemento `variable` può essere assegnato in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="17db0-113">For the `variable` element, the value is also assigned in several ways.</span></span> <span data-ttu-id="17db0-114">È possibile assegnarlo tramite il contenuto restituito dall'espressione XPath nell'attributo `select` oppure usando il contenuto del corpo del modello.</span><span class="sxs-lookup"><span data-stu-id="17db0-114">You can assign it by returning content from the XPath expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="17db0-115">Da entrambi gli elementi `parameter` e `variable`, se viene assegnato un valore dall'espressione XPath, viene restituito uno dei quattro tipi XPath principali: Boolean, string, number o node set.</span><span class="sxs-lookup"><span data-stu-id="17db0-115">For both the `parameter` and `variable` elements, if a value is assigned by the XPath expression, then one of the four basic XPath types will be returned: Boolean, string, number, or node set.</span></span> <span data-ttu-id="17db0-116">Se il valore viene assegnato usando un corpo del modello non vuoto, verrà restituito un tipo di dati non XPath, ovvero un frammento di albero risultato.</span><span class="sxs-lookup"><span data-stu-id="17db0-116">When the value is given by using a non-empty template body, then a non-XPath data type is returned, and that will be a result tree fragment.</span></span>

<span data-ttu-id="17db0-117">Una query XPath restituisce un tipo di dati che non appartiene a uno dei quattro tipi di oggetti XPath unicamente nel caso in cui una variabile è associata a un frammento di albero risultato, anziché a uno dei quattro tipi di dati XPath di base.</span><span class="sxs-lookup"><span data-stu-id="17db0-117">When a variable is bound to a result tree fragment instead of one of the four basic XPath data types, this is the only time that an XPath query returns a type that is not one of the four XPath object types.</span></span> <span data-ttu-id="17db0-118">I frammenti di albero risultato e il relativo comportamento sono descritti nella [specifica World Wide Web Consortium (W3C)](https://www.w3.org/TR/xslt-10/), dalla [sezione 11.1 Result Tree Fragments](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments) (Frammenti di albero risultato) alla [sezione 11.6 Passing Parameters to Templates](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates) (Passaggio di parametri ai modelli).</span><span class="sxs-lookup"><span data-stu-id="17db0-118">Result tree fragments and their behavior are discussed in the [World Wide Web Consortium (W3C) specification](https://www.w3.org/TR/xslt-10/), [section 11.1 Result Tree Fragments](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments) through [section 11.6 Passing Parameters to Templates](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates).</span></span> <span data-ttu-id="17db0-119">Nell'[introduzione alla sezione 1](https://www.w3.org/TR/xslt-10/#section-Introduction) viene inoltre illustrato come i modelli possano contenere elementi dello spazio dei nomi XSLT che restituiscono o creano frammenti di albero risultato.</span><span class="sxs-lookup"><span data-stu-id="17db0-119">Also, [section 1 Introduction](https://www.w3.org/TR/xslt-10/#section-Introduction) discusses how templates can contain elements from the XSLT namespace that return or create result tree fragments.</span></span>

<span data-ttu-id="17db0-120">Un frammento di albero risultato si comporta, teoricamente, come un set di nodi con un unico nodo radice,</span><span class="sxs-lookup"><span data-stu-id="17db0-120">A result tree fragment, in concept, behaves like a node set with nothing more than a single root node.</span></span> <span data-ttu-id="17db0-121">mentre gli altri nodi restituiti sono nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="17db0-121">However, the rest of the nodes returned are child nodes.</span></span> <span data-ttu-id="17db0-122">Per visualizzare i nodi figlio a livello di codice, copiare il frammento di albero risultato nell'albero risultato stessa usando l'elemento `<xsl:copy-of>`.</span><span class="sxs-lookup"><span data-stu-id="17db0-122">To programmatically see the child nodes, copy the result tree fragment to the result tree using the `<xsl:copy-of>` element.</span></span> <span data-ttu-id="17db0-123">Questa operazione consente di copiare in sequenza tutti i nodi figlio nell'albero risultato.</span><span class="sxs-lookup"><span data-stu-id="17db0-123">When the copy-of is performed, all the child nodes are also copied to the result tree in sequence.</span></span> <span data-ttu-id="17db0-124">Il frammento di albero risultato non farà parte dell'albero risultato o dell'output della trasformazione finché non viene usato un comando `copy` o `copy-of`.</span><span class="sxs-lookup"><span data-stu-id="17db0-124">Until a `copy` or `copy-of` is used, a result tree fragment is not part of the result tree or the output from the transformation.</span></span>

<span data-ttu-id="17db0-125">Per eseguire un'iterazione sui nodi restituiti in un frammento di albero risultato, usare <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="17db0-125">To iterate over the returned nodes of a result tree fragment, an <xref:System.Xml.XPath.XPathNavigator> is used.</span></span> <span data-ttu-id="17db0-126">Nel codice di esempio seguente viene illustrata la creazione di un frammento di albero risultato in un foglio di stile, chiamando la funzione con un parametro `fragment` contenente dati XML.</span><span class="sxs-lookup"><span data-stu-id="17db0-126">The following code sample shows how to create a result tree fragment within a style sheet by calling the function with a parameter `fragment`, which contains XML.</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:var name="fragment">
        <node1>
            <node2/>
        </node1>
    <xsl:var>

  <msxsl:script language="C#" implements-prefix="user">
    function NodeFragment(XPathNavigator nav)
    {
      if (nav.HasSelection == false)
        XPathNavigator.MoveToNext();
      return;
    }
  </msxsl:script>

    <xsl:template match="/">
            <xsl:value-of select="user:NodeFragment(msxml:node-set($fragment))"/>
    </xsl:template>
</xsl:stylesheet>
```

<span data-ttu-id="17db0-127">Di seguito è riportato un altro esempio in cui viene mostrata una variabile, in RTF (Rich Text Format) e, di conseguenza, un tipo di frammento di albero risultato nodo non convertito in un set di nodi.</span><span class="sxs-lookup"><span data-stu-id="17db0-127">Here is another sample showing a variable, which is in Rich Text Format (RTF), and hence, a type of result tree fragment, that is not converted to a node set.</span></span> <span data-ttu-id="17db0-128">Il frammento viene passato a una funzione script e per esplorare i nodi viene usato il tipo <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="17db0-128">Instead, it is passed to a script function, and the <xref:System.Xml.XPath.XPathNavigator> is used to navigate over the nodes.</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNavigator nav)
    {
        bool b = nav.MoveToFirstChild();
        if (b)
            return nav.Value;
        else
            return "Does not exist";
    }

]]>

</msxsl:script>

<xsl:template match="/">
    <first_book>
        <xsl:value-of select="user:func($node-fragment)"/>
    </first_book>
</xsl:template>

</xsl:stylesheet>
```

<span data-ttu-id="17db0-129">Il risultato della trasformazione dei dati XML ottenuto usando questo foglio di stile è illustrato nell'output seguente.</span><span class="sxs-lookup"><span data-stu-id="17db0-129">The result of transforming any XML with this style sheet is shown in the following output.</span></span>

## <a name="output"></a><span data-ttu-id="17db0-130">Output</span><span class="sxs-lookup"><span data-stu-id="17db0-130">Output</span></span>

```xml
<first_book xmlns:user="urn:books">Book1</first_book>
```

<span data-ttu-id="17db0-131">Come descritto in precedenza, la funzione `node-set` consente di convertire un frammento di albero risultato in un set di nodi.</span><span class="sxs-lookup"><span data-stu-id="17db0-131">As stated above, the `node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="17db0-132">Il nodo risultante contiene sempre un nodo singolo, costituito dal nodo radice dell'albero.</span><span class="sxs-lookup"><span data-stu-id="17db0-132">The resulting node always contains a single node that is the root node of the tree.</span></span> <span data-ttu-id="17db0-133">Se un frammento di albero risultato viene convertito in un set di nodi, potrà essere usato come un normale set di nodi, ad esempio in un'istruzione for-each oppure nel valore di un attributo `select`.</span><span class="sxs-lookup"><span data-stu-id="17db0-133">If you convert a result tree fragment to a node set, then you can use it anywhere a regular node set is used, such as in a for-each statement or in the value of a `select` attribute.</span></span> <span data-ttu-id="17db0-134">Nelle righe di codice seguenti viene mostrato un frammento convertito in un set di nodi e usato come tale:</span><span class="sxs-lookup"><span data-stu-id="17db0-134">The following lines of code show the fragment being converted to a node set and used as a node set:</span></span>

`<xsl:for-each select="msxsl:node-set($node-fragment)">`

`<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`

<span data-ttu-id="17db0-135">Per esplorare un frammento convertito in un set di nodi non viene più usato <xref:System.Xml.XPath.XPathNavigator>, bensì</span><span class="sxs-lookup"><span data-stu-id="17db0-135">When a fragment is converted to a node set, you no longer use the <xref:System.Xml.XPath.XPathNavigator> to navigate over it.</span></span> <span data-ttu-id="17db0-136"><xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="17db0-136">For a node set, you use the <xref:System.Xml.XPath.XPathNodeIterator> instead.</span></span>

<span data-ttu-id="17db0-137">Nell'esempio seguente `$var` è una variabile che rappresenta l'albero dei nodi del foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="17db0-137">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="17db0-138">L'istruzione for-each combinata con la funzione `node-set` consente all'utente di eseguire un'iterazione su questo albero come set di nodi.</span><span class="sxs-lookup"><span data-stu-id="17db0-138">The for-each statement, combined with the `node-set` function, allows the user to iterate over this tree as a node set.</span></span>

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:variable name="states">
        <node1>AL</node1>
        <node1>CA</node1>
        <node1>CO</node1>
        <node1>WA</node1>
    </xsl:variable>

    <xsl:template match="/">
            <xsl:for-each select="msxsl:node-set($states)"/>
    </xsl:template>
</xsl:stylesheet>
```

<span data-ttu-id="17db0-139">Di seguito è riportato un altro esempio di variabile in formato RTF, quindi di tipo frammento di albero risultato, convertita in set di nodi prima di essere passata a una funzione script come "XPathNodeIterator".</span><span class="sxs-lookup"><span data-stu-id="17db0-139">Here is another example of a variable that is in RTF, and hence of type result tree fragment, that is converted to a node set before being passed to a script function as XPathNodeIterator.</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNodeIterator it)
    {
        it.MoveNext();
        return it.Current.Value;
        //it.Current returns XPathNavigator positioned on the current node
    }

]]>

</msxsl:script>
<xsl:template match="/">
    <books>
        <xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>
    </books>
</xsl:template>

</xsl:stylesheet>
```

<span data-ttu-id="17db0-140">Il risultato della trasformazione di dati XML con il presente foglio di stile è il seguente:</span><span class="sxs-lookup"><span data-stu-id="17db0-140">The following is the result of transforming XML with this style sheet:</span></span>

```xml
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>
```

## <a name="see-also"></a><span data-ttu-id="17db0-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17db0-141">See also</span></span>

- <xref:System.Xml.XPath.XPathNodeIterator>
- [<span data-ttu-id="17db0-142">Trasformazioni XSLT con la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="17db0-142">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="17db0-143">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="17db0-143">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
