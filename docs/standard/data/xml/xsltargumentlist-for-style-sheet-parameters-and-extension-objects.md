---
title: XsltArgumentList per i parametri dei fogli di stile e gli oggetti di estensione
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: de2f0dce-6b98-4908-bba7-ed150cc50355
ms.openlocfilehash: 34ffb9923337bbad90b2170a16d610d26c7f6f23
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160196"
---
# <a name="xsltargumentlist-for-style-sheet-parameters-and-extension-objects"></a><span data-ttu-id="7fc96-102">XsltArgumentList per i parametri dei fogli di stile e gli oggetti di estensione</span><span class="sxs-lookup"><span data-stu-id="7fc96-102">XsltArgumentList for Style Sheet Parameters and Extension Objects</span></span>
<span data-ttu-id="7fc96-103">La classe <xref:System.Xml.Xsl.XsltArgumentList> contiene parametri Extensible Stylesheet Language for Transformations (XSLT) e oggetti di estensione XSLT.</span><span class="sxs-lookup"><span data-stu-id="7fc96-103">The <xref:System.Xml.Xsl.XsltArgumentList> class contains Extensible Stylesheet Language for Transformations (XSLT) parameters and XSLT extension objects.</span></span> <span data-ttu-id="7fc96-104">Quando vengono passati al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, questi parametri e oggetti di estensione possono essere richiamati dai fogli di stile.</span><span class="sxs-lookup"><span data-stu-id="7fc96-104">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fc96-105">Le classi <xref:System.Xml.Xsl.XslTransform> e <xref:System.Xml.Xsl.XsltArgumentList> sono obsolete in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="7fc96-105">The <xref:System.Xml.Xsl.XslTransform> and <xref:System.Xml.Xsl.XsltArgumentList> classes are obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="7fc96-106">È possibile eseguire le trasformazioni XSLT usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="7fc96-106">You can perform XSLT transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="7fc96-107">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="7fc96-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="7fc96-108">La classe <xref:System.Xml.Xsl.XsltArgumentList> contiene i parametri XSLT e gli oggetti di estensione XSLT.</span><span class="sxs-lookup"><span data-stu-id="7fc96-108">The <xref:System.Xml.Xsl.XsltArgumentList> class contains XSLT parameters and XSLT extension objects.</span></span> <span data-ttu-id="7fc96-109">Quando vengono passati al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, questi parametri e oggetti di estensione possono essere richiamati dai fogli di stile.</span><span class="sxs-lookup"><span data-stu-id="7fc96-109">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
 <span data-ttu-id="7fc96-110">I vantaggi del passaggio di un oggetto rispetto all'uso di uno script incorporato sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7fc96-110">The following are advantages to passing an object rather than using an embedded script:</span></span>  
  
- <span data-ttu-id="7fc96-111">Migliore incapsulamento e riutilizzo delle classi.</span><span class="sxs-lookup"><span data-stu-id="7fc96-111">Provides better encapsulation and reuse of classes.</span></span>  
  
- <span data-ttu-id="7fc96-112">Fogli di stile di dimensioni minori e più gestibili.</span><span class="sxs-lookup"><span data-stu-id="7fc96-112">Allows style sheets to be smaller and more maintainable.</span></span>  
  
- <span data-ttu-id="7fc96-113">Supporto della chiamata ai metodi nelle classi appartenenti a spazi dei nomi diversi da quelli definiti nel set degli spazi dei nomi <xref:System> supportati.</span><span class="sxs-lookup"><span data-stu-id="7fc96-113">Supports calling methods on classes belonging to namespaces other than those defined within the set of supported <xref:System> namespaces.</span></span>  
  
- <span data-ttu-id="7fc96-114">Possibilità di passare i frammenti di albero risultato al foglio di stile usando <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="7fc96-114">Supports passing result tree fragments to the style sheet with the use of the <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
## <a name="xslt-style-sheet-parameters"></a><span data-ttu-id="7fc96-115">Parametri dei fogli di stile XSLT</span><span class="sxs-lookup"><span data-stu-id="7fc96-115">XSLT Style Sheet Parameters</span></span>  
 <span data-ttu-id="7fc96-116">I parametri XSLT vengono aggiunti all'elenco <xref:System.Xml.Xsl.XsltArgumentList> mediante il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fc96-116">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="7fc96-117">Un nome completo e un URI dello spazio dei nomi sono associati all'oggetto parametro in quel momento.</span><span class="sxs-lookup"><span data-stu-id="7fc96-117">A qualified name and namespace Uniform Resource Identifier (URI) are associated with the parameter object at that time.</span></span>  
  
 <span data-ttu-id="7fc96-118">L'oggetto parameter deve corrispondere a un tipo W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="7fc96-118">The parameter object should correspond to a World Wide Web Consortium (W3C) type.</span></span> <span data-ttu-id="7fc96-119">La tabella seguente illustra i tipi W3C corrispondenti, le classi .NET Framework equivalenti (tipo) e se il tipo W3C è un tipo XML Path Language (XPath) o XSLT.</span><span class="sxs-lookup"><span data-stu-id="7fc96-119">The following table shows the corresponding W3C types, the equivalent .NET Framework classes (type), and whether the W3C type is an XML Path Language (XPath) type or XSLT type.</span></span>  
  
|<span data-ttu-id="7fc96-120">Tipo W3C</span><span class="sxs-lookup"><span data-stu-id="7fc96-120">W3C Type</span></span>|<span data-ttu-id="7fc96-121">Classe .NET Framework equivalente (tipo)</span><span class="sxs-lookup"><span data-stu-id="7fc96-121">Equivalent .NET Framework class (type)</span></span>|<span data-ttu-id="7fc96-122">Tipo XPath o tipo XSLT</span><span class="sxs-lookup"><span data-stu-id="7fc96-122">XPath type or XSLT type</span></span>|  
|--------------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="7fc96-123">string</span><span class="sxs-lookup"><span data-stu-id="7fc96-123">String</span></span>|<span data-ttu-id="7fc96-124">System.String</span><span class="sxs-lookup"><span data-stu-id="7fc96-124">System.String</span></span>|<span data-ttu-id="7fc96-125">XPath</span><span class="sxs-lookup"><span data-stu-id="7fc96-125">XPath</span></span>|  
|<span data-ttu-id="7fc96-126">Boolean</span><span class="sxs-lookup"><span data-stu-id="7fc96-126">Boolean</span></span>|<span data-ttu-id="7fc96-127">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="7fc96-127">System.Boolean</span></span>|<span data-ttu-id="7fc96-128">XPath</span><span class="sxs-lookup"><span data-stu-id="7fc96-128">XPath</span></span>|  
|<span data-ttu-id="7fc96-129">Number</span><span class="sxs-lookup"><span data-stu-id="7fc96-129">Number</span></span>|<span data-ttu-id="7fc96-130">System.Double</span><span class="sxs-lookup"><span data-stu-id="7fc96-130">System.Double</span></span>|<span data-ttu-id="7fc96-131">XPath</span><span class="sxs-lookup"><span data-stu-id="7fc96-131">XPath</span></span>|  
|<span data-ttu-id="7fc96-132">Frammento di albero risultato</span><span class="sxs-lookup"><span data-stu-id="7fc96-132">Result Tree Fragment</span></span>|<span data-ttu-id="7fc96-133">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7fc96-133">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="7fc96-134">XSLT</span><span class="sxs-lookup"><span data-stu-id="7fc96-134">XSLT</span></span>|  
|<span data-ttu-id="7fc96-135">Node set</span><span class="sxs-lookup"><span data-stu-id="7fc96-135">Node Set</span></span>|<span data-ttu-id="7fc96-136">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="7fc96-136">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="7fc96-137">XPath</span><span class="sxs-lookup"><span data-stu-id="7fc96-137">XPath</span></span>|  
  
 <span data-ttu-id="7fc96-138">Se l'oggetto parameter non fa parte di una delle classi sopra elencate, è obbligato a essere Double o String, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7fc96-138">If the parameter object is not one of the above classes, it is forced to either a Double or String, as appropriate.</span></span> <span data-ttu-id="7fc96-139">I tipi Int16, UInt16, Int32, UInt32, Int64, UInt64, Single e Decimal sono obbligati a essere Double.</span><span class="sxs-lookup"><span data-stu-id="7fc96-139">Int16, UInt16, Int32, UInt32, Int64, UInt64, Single and Decimal types are forced to a Double.</span></span> <span data-ttu-id="7fc96-140">Tutti gli altri tipi sono obbligati a essere uno String usando il metodo `ToString`.</span><span class="sxs-lookup"><span data-stu-id="7fc96-140">All other types are forced to a String using the `ToString` method.</span></span>  
  
#### <a name="to-use-the-xslt-parameter-the-user-needs-to-do-the-following"></a><span data-ttu-id="7fc96-141">Per usare il parametro XSLT, è necessario:</span><span class="sxs-lookup"><span data-stu-id="7fc96-141">To use the XSLT parameter, the user needs to do the following:</span></span>  
  
1. <span data-ttu-id="7fc96-142">Creare un <xref:System.Xml.Xsl.XsltArgumentList> e aggiungere gli oggetti usando <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fc96-142">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the objects using <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span></span>  
  
2. <span data-ttu-id="7fc96-143">Richiamare i parametri dal foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="7fc96-143">Call the parameters from the style sheet.</span></span>  
  
3. <span data-ttu-id="7fc96-144">Passare l'oggetto <xref:System.Xml.Xsl.XsltArgumentList> al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> .</span><span class="sxs-lookup"><span data-stu-id="7fc96-144">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="7fc96-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fc96-145">Example</span></span>  
 <span data-ttu-id="7fc96-146">Nell'esempio seguente il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> viene usato per contenere una data di sconto calcolato.</span><span class="sxs-lookup"><span data-stu-id="7fc96-146">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold a calculated discount date.</span></span> <span data-ttu-id="7fc96-147">La data di sconto è calcolata dopo 20 giorni dalla data dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="7fc96-147">The discount date is calculated to be 20 days from the order date.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public class Sample  
  
   Private Const filename As String = "order.xml"  
   Private Const stylesheet As String = "discount.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Calculate the discount date.  
    Dim today As DateTime = DateTime.Now  
    Dim d As DateTime = today.AddDays(20)  
    xslArg.AddParam("discount", "", d.ToString())  
  
    'Create an XmlTextWriter to handle the output.  
    Dim writer As XmlTextWriter = New XmlTextWriter("orderout.xml", Nothing)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
  
    writer.Close()  
  
  End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "order.xml";  
   private const String stylesheet = "discount.xsl";  
  
   public static void Main() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Calculate the discount date.  
    DateTime today = DateTime.Now;  
    DateTime d = today.AddDays(20);  
    xslArg.AddParam("discount", "", d.ToString());  
  
    //Create an XmlTextWriter to handle the output.  
    XmlTextWriter writer = new XmlTextWriter("orderout.xml", null);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  }  
}  
```  
  
### <a name="input"></a><span data-ttu-id="7fc96-148">Input</span><span class="sxs-lookup"><span data-stu-id="7fc96-148">Input</span></span>  
 <span data-ttu-id="7fc96-149">order.xml</span><span class="sxs-lookup"><span data-stu-id="7fc96-149">order.xml</span></span>  
  
```xml  
<!--Represents a customer order-->  
<order>  
  <book ISBN='10-861003-324'>  
    <title>The Handmaid's Tale</title>  
    <price>19.95</price>  
  </book>  
  <cd ISBN='2-3631-4'>  
    <title>Americana</title>  
    <price>16.95</price>  
  </cd>  
</order>  
```  
  
 <span data-ttu-id="7fc96-150">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="7fc96-150">discount.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">  
  <xsl:param name="discount"/>  
  <xsl:template match="/">  
    <order>  
      <xsl:variable name="sub-total" select="sum(//price)"/>  
      <total><xsl:value-of select="$sub-total"/></total>  
      15% discount if paid by: <xsl:value-of select="$discount"/>  
    </order>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a><span data-ttu-id="7fc96-151">Output</span><span class="sxs-lookup"><span data-stu-id="7fc96-151">Output</span></span>  
  
```xml  
<order>  
   <total>36.9</total>
   15% discount if paid by: 5/6/2001 5:01:15 PM
</order>  
```  
  
## <a name="xslt-extension-objects"></a><span data-ttu-id="7fc96-152">Oggetti di estensione XSLT</span><span class="sxs-lookup"><span data-stu-id="7fc96-152">XSLT Extension Objects</span></span>  
 <span data-ttu-id="7fc96-153">Gli oggetti di estensione XSLT vengono aggiunti all'elenco <xref:System.Xml.Xsl.XsltArgumentList> usando il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fc96-153">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="7fc96-154">Un nome completo e un URI dello spazio dei nomi sono associati all'oggetto di estensione in quel momento.</span><span class="sxs-lookup"><span data-stu-id="7fc96-154">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
 <span data-ttu-id="7fc96-155">Quando un oggetto viene aggiunto, il chiamante del metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> deve essere completamente attendibile secondo il criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7fc96-155">When an object is added, the caller of the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> must be fully trusted in the security policy.</span></span> <span data-ttu-id="7fc96-156">Se il chiamante è di tipo semi-trusted, l'aggiunta avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="7fc96-156">If the caller is semi-trusted, the addition will fail.</span></span>  
  
 <span data-ttu-id="7fc96-157">Anche se un oggetto viene aggiunto correttamente, questo non significa che l'esecuzione avverrà correttamente.</span><span class="sxs-lookup"><span data-stu-id="7fc96-157">Though an object is added successfully, it does not guarantee that the execution will be successful.</span></span> <span data-ttu-id="7fc96-158">Quando viene chiamato il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, le autorizzazioni vengono calcolate in base all'evidenza fornita nella fase <xref:System.Xml.Xsl.XslTransform.Load%2A> e il set di autorizzazioni viene assegnato all'intero processo di trasformazione.</span><span class="sxs-lookup"><span data-stu-id="7fc96-158">When the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is called, permissions are calculated against the evidence provided at <xref:System.Xml.Xsl.XslTransform.Load%2A> time, and that permission set is assigned to the entire transformation process.</span></span> <span data-ttu-id="7fc96-159">Se un oggetto di estensione tenta di avviare un'azione che necessita di autorizzazioni non presenti nel set, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7fc96-159">If an extension object attempts to initiate an action that requires permissions not found in the set, an exception is thrown.</span></span>  
  
 <span data-ttu-id="7fc96-160">Dagli oggetti di estensione vengono restituiti dati appartenenti a uno dei quattro tipi di dati XPath principali, e cioè number, string, boolean o node set.</span><span class="sxs-lookup"><span data-stu-id="7fc96-160">The data types returned from extension objects are one of the four basic XPath data types of number, string, Boolean, and node set.</span></span>  
  
#### <a name="to-use-the-xslt-extension-object-the-user-needs-to-do-the-following"></a><span data-ttu-id="7fc96-161">Per usare l'oggetto di estensione XSLT, è necessario:</span><span class="sxs-lookup"><span data-stu-id="7fc96-161">To use the XSLT extension object, the user needs to do the following:</span></span>  
  
1. <span data-ttu-id="7fc96-162">Creare un <xref:System.Xml.Xsl.XsltArgumentList> e aggiungere l'oggetto di estensione usando <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fc96-162">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span></span>  
  
2. <span data-ttu-id="7fc96-163">Richiamare l'oggetto di estensione dal foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="7fc96-163">Invoke the extension object from the style sheet.</span></span>  
  
3. <span data-ttu-id="7fc96-164">Passare l'oggetto <xref:System.Xml.Xsl.XsltArgumentList> al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> .</span><span class="sxs-lookup"><span data-stu-id="7fc96-164">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="7fc96-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fc96-165">Example</span></span>  
 <span data-ttu-id="7fc96-166">Nell'esempio seguente viene calcolata la circonferenza di un cerchio di cui viene fornito il raggio.</span><span class="sxs-lookup"><span data-stu-id="7fc96-166">The following example calculates the circumference of a circle given its radius.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "circle.xsl"  
  
   Public Shared Sub Main()  
        Dim test As Sample = New Sample  
   End Sub  
  
  Public Sub New()  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Add an object to calculate the circumference of the circle.  
    Dim obj As Calculate = New Calculate  
    xslArg.AddExtensionObject("urn:myObj", obj)  
  
    'Create an XmlTextWriter to output to the console.  
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
    writer.Close()  
  
  End Sub  
  
  'Calculates the circumference of a circle given the radius.  
  Public Class Calculate  
  
    Private circ As double = 0  
  
    Public Function Circumference(radius As Double) As Double  
       circ = Math.PI*2*radius  
       Return circ  
    End Function  
  End Class  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "number.xml";  
   private const String stylesheet = "circle.xsl";  
  
   public static void Main() {  
  
        Sample test = new Sample();  
    }  
  
  public Sample() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Add an object to calculate the circumference of the circle.  
    Calculate obj = new Calculate();  
    xslArg.AddExtensionObject("urn:myObj", obj);  
  
    //Create an XmlTextWriter to output to the console.  
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  
  }  
  
  //Calculates the circumference of a circle given the radius.  
  public class Calculate {  
  
    private double circ = 0;  
  
    public double Circumference(double radius){  
       circ = Math.PI*2*radius;  
       return circ;  
    }  
  }  
}  
```  
  
### <a name="input"></a><span data-ttu-id="7fc96-167">Input</span><span class="sxs-lookup"><span data-stu-id="7fc96-167">Input</span></span>  
 <span data-ttu-id="7fc96-168">number.xml</span><span class="sxs-lookup"><span data-stu-id="7fc96-168">number.xml</span></span>  
  
```xml  
<?xml version='1.0'?>  
<data>  
  <circle>  
    <radius>12</radius>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
  </circle>  
</data>
```  
  
 <span data-ttu-id="7fc96-169">circle.xsl</span><span class="sxs-lookup"><span data-stu-id="7fc96-169">circle.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:myObj="urn:myObj">  
  
  <xsl:template match="data">  
  <circles>  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="myObj:Circumference(radius)"/>
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a><span data-ttu-id="7fc96-170">Output</span><span class="sxs-lookup"><span data-stu-id="7fc96-170">Output</span></span>  
 `<circles xmlns:myObj="urn:myObj">`  
  
 `<circle>`  
  
 `<radius>12</radius>`  
  
 `<circumference>75.398223686155</circumference>`  
  
 `</circle>`  
  
 `<circle>`  
  
 `<radius>37.5</radius>`  
  
 `<circumference>235.61944901923448</circumference>`  
  
 `</circle>`  
  
 `</circles>`  
  
## <a name="see-also"></a><span data-ttu-id="7fc96-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fc96-171">See also</span></span>

- [<span data-ttu-id="7fc96-172">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="7fc96-172">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
