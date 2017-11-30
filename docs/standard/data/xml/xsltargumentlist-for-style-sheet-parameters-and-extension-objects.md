---
title: XsltArgumentList per i parametri dei fogli di stile e gli oggetti di estensione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: de2f0dce-6b98-4908-bba7-ed150cc50355
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4741551b1e6dd2694a0bd65e65a15953f808e59
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xsltargumentlist-for-style-sheet-parameters-and-extension-objects"></a><span data-ttu-id="3b9ad-102">XsltArgumentList per i parametri dei fogli di stile e gli oggetti di estensione</span><span class="sxs-lookup"><span data-stu-id="3b9ad-102">XsltArgumentList for Style Sheet Parameters and Extension Objects</span></span>
<span data-ttu-id="3b9ad-103">La classe <xref:System.Xml.Xsl.XsltArgumentList> contiene parametri Extensible Stylesheet Language for Transformations (XSLT) e oggetti di estensione XSLT.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-103">The <xref:System.Xml.Xsl.XsltArgumentList> class contains Extensible Stylesheet Language for Transformations (XSLT) parameters and XSLT extension objects.</span></span> <span data-ttu-id="3b9ad-104">Quando vengono passati al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, questi parametri e oggetti di estensione possono essere richiamati dai fogli di stile.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-104">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b9ad-105">Le classi <xref:System.Xml.Xsl.XslTransform> e <xref:System.Xml.Xsl.XsltArgumentList> sono obsolete in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b9ad-105">The <xref:System.Xml.Xsl.XslTransform> and <xref:System.Xml.Xsl.XsltArgumentList> classes are obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="3b9ad-106">È possibile eseguire le trasformazioni XSLT usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-106">You can perform XSLT transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="3b9ad-107">Vedere [utilizzando la classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [la migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="3b9ad-108">La classe <xref:System.Xml.Xsl.XsltArgumentList> contiene i parametri XSLT e gli oggetti di estensione XSLT.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-108">The <xref:System.Xml.Xsl.XsltArgumentList> class contains XSLT parameters and XSLT extension objects.</span></span> <span data-ttu-id="3b9ad-109">Quando vengono passati al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, questi parametri e oggetti di estensione possono essere richiamati dai fogli di stile.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-109">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
 <span data-ttu-id="3b9ad-110">I vantaggi del passaggio di un oggetto rispetto all'uso di uno script incorporato sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b9ad-110">The following are advantages to passing an object rather than using an embedded script:</span></span>  
  
-   <span data-ttu-id="3b9ad-111">Migliore incapsulamento e riutilizzo delle classi.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-111">Provides better encapsulation and reuse of classes.</span></span>  
  
-   <span data-ttu-id="3b9ad-112">Fogli di stile di dimensioni minori e più gestibili.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-112">Allows style sheets to be smaller and more maintainable.</span></span>  
  
-   <span data-ttu-id="3b9ad-113">Supporto della chiamata ai metodi nelle classi appartenenti a spazi dei nomi diversi da quelli definiti nel set degli spazi dei nomi <xref:System> supportati.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-113">Supports calling methods on classes belonging to namespaces other than those defined within the set of supported <xref:System> namespaces.</span></span>  
  
-   <span data-ttu-id="3b9ad-114">Possibilità di passare i frammenti di albero risultato al foglio di stile usando <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-114">Supports passing result tree fragments to the style sheet with the use of the <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
## <a name="xslt-style-sheet-parameters"></a><span data-ttu-id="3b9ad-115">Parametri dei fogli di stile XSLT</span><span class="sxs-lookup"><span data-stu-id="3b9ad-115">XSLT Style Sheet Parameters</span></span>  
 <span data-ttu-id="3b9ad-116">I parametri XSLT vengono aggiunti all'elenco <xref:System.Xml.Xsl.XsltArgumentList> mediante il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-116">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="3b9ad-117">Un nome completo e un URI dello spazio dei nomi sono associati all'oggetto parametro in quel momento.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-117">A qualified name and namespace Uniform Resource Identifier (URI) are associated with the parameter object at that time.</span></span>  
  
 <span data-ttu-id="3b9ad-118">L'oggetto parameter deve corrispondere a un tipo W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="3b9ad-118">The parameter object should correspond to a World Wide Web Consortium (W3C) type.</span></span> <span data-ttu-id="3b9ad-119">Nella tabella seguente sono illustrati i tipi W3C corrispondenti e le classi [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] equivalenti (tipo) e viene indicato se il tipo W3C è un tipo XPath o XSLT.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-119">The following table shows the corresponding W3C types, the equivalent [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes (type), and whether the W3C type is an XML Path Language (XPath) type or XSLT type.</span></span>  
  
|<span data-ttu-id="3b9ad-120">Tipo W3C</span><span class="sxs-lookup"><span data-stu-id="3b9ad-120">W3C Type</span></span>|<span data-ttu-id="3b9ad-121">Classi di .NET Framework equivalenti (tipo)</span><span class="sxs-lookup"><span data-stu-id="3b9ad-121">Equivalent .NET Framework class (type)</span></span>|<span data-ttu-id="3b9ad-122">Tipo XPath o tipo XSLT</span><span class="sxs-lookup"><span data-stu-id="3b9ad-122">XPath type or XSLT type</span></span>|  
|--------------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="3b9ad-123">String</span><span class="sxs-lookup"><span data-stu-id="3b9ad-123">String</span></span>|<span data-ttu-id="3b9ad-124">System.String</span><span class="sxs-lookup"><span data-stu-id="3b9ad-124">System.String</span></span>|<span data-ttu-id="3b9ad-125">XPath</span><span class="sxs-lookup"><span data-stu-id="3b9ad-125">XPath</span></span>|  
|<span data-ttu-id="3b9ad-126">Boolean</span><span class="sxs-lookup"><span data-stu-id="3b9ad-126">Boolean</span></span>|<span data-ttu-id="3b9ad-127">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="3b9ad-127">System.Boolean</span></span>|<span data-ttu-id="3b9ad-128">XPath</span><span class="sxs-lookup"><span data-stu-id="3b9ad-128">XPath</span></span>|  
|<span data-ttu-id="3b9ad-129">Numero</span><span class="sxs-lookup"><span data-stu-id="3b9ad-129">Number</span></span>|<span data-ttu-id="3b9ad-130">System.Double</span><span class="sxs-lookup"><span data-stu-id="3b9ad-130">System.Double</span></span>|<span data-ttu-id="3b9ad-131">XPath</span><span class="sxs-lookup"><span data-stu-id="3b9ad-131">XPath</span></span>|  
|<span data-ttu-id="3b9ad-132">Frammento di albero risultato</span><span class="sxs-lookup"><span data-stu-id="3b9ad-132">Result Tree Fragment</span></span>|<span data-ttu-id="3b9ad-133">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="3b9ad-133">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="3b9ad-134">XSLT</span><span class="sxs-lookup"><span data-stu-id="3b9ad-134">XSLT</span></span>|  
|<span data-ttu-id="3b9ad-135">Node set</span><span class="sxs-lookup"><span data-stu-id="3b9ad-135">Node Set</span></span>|<span data-ttu-id="3b9ad-136">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="3b9ad-136">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="3b9ad-137">XPath</span><span class="sxs-lookup"><span data-stu-id="3b9ad-137">XPath</span></span>|  
  
 <span data-ttu-id="3b9ad-138">Se l'oggetto parameter non fa parte di una delle classi sopra elencate, è obbligato a essere Double o String, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-138">If the parameter object is not one of the above classes, it is forced to either a Double or String, as appropriate.</span></span> <span data-ttu-id="3b9ad-139">I tipi Int16, UInt16, Int32, UInt32, Int64, UInt64, Single e Decimal sono obbligati a essere Double.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-139">Int16, UInt16, Int32, UInt32, Int64, UInt64, Single and Decimal types are forced to a Double.</span></span> <span data-ttu-id="3b9ad-140">Tutti gli altri tipi sono obbligati a essere uno String usando il metodo `ToString`.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-140">All other types are forced to a String using the `ToString` method.</span></span>  
  
#### <a name="to-use-the-xslt-parameter-the-user-needs-to-do-the-following"></a><span data-ttu-id="3b9ad-141">Per usare il parametro XSLT, è necessario:</span><span class="sxs-lookup"><span data-stu-id="3b9ad-141">To use the XSLT parameter, the user needs to do the following:</span></span>  
  
1.  <span data-ttu-id="3b9ad-142">Creare un <xref:System.Xml.Xsl.XsltArgumentList> e aggiungere gli oggetti usando <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-142">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the objects using <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span></span>  
  
2.  <span data-ttu-id="3b9ad-143">Richiamare i parametri dal foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-143">Call the parameters from the style sheet.</span></span>  
  
3.  <span data-ttu-id="3b9ad-144">Passare l'oggetto <xref:System.Xml.Xsl.XsltArgumentList> al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> .</span><span class="sxs-lookup"><span data-stu-id="3b9ad-144">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="3b9ad-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b9ad-145">Example</span></span>  
 <span data-ttu-id="3b9ad-146">Nell'esempio seguente il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> viene usato per contenere una data di sconto calcolato.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-146">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold a calculated discount date.</span></span> <span data-ttu-id="3b9ad-147">La data di sconto è calcolata dopo 20 giorni dalla data dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-147">The discount date is calculated to be 20 days from the order date.</span></span>  
  
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
  
### <a name="input"></a><span data-ttu-id="3b9ad-148">Input</span><span class="sxs-lookup"><span data-stu-id="3b9ad-148">Input</span></span>  
 <span data-ttu-id="3b9ad-149">order.xml</span><span class="sxs-lookup"><span data-stu-id="3b9ad-149">order.xml</span></span>  
  
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
  
 <span data-ttu-id="3b9ad-150">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="3b9ad-150">discount.xsl</span></span>  
  
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
  
### <a name="output"></a><span data-ttu-id="3b9ad-151">Output</span><span class="sxs-lookup"><span data-stu-id="3b9ad-151">Output</span></span>  
  
```xml  
<order>  
   <total>36.9</total>   
   15% discount if paid by: 5/6/2001 5:01:15 PM   
</order>  
```  
  
## <a name="xslt-extension-objects"></a><span data-ttu-id="3b9ad-152">Oggetti di estensione XSLT</span><span class="sxs-lookup"><span data-stu-id="3b9ad-152">XSLT Extension Objects</span></span>  
 <span data-ttu-id="3b9ad-153">Gli oggetti di estensione XSLT vengono aggiunti all'elenco <xref:System.Xml.Xsl.XsltArgumentList> usando il metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-153">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="3b9ad-154">Un nome completo e un URI dello spazio dei nomi sono associati all'oggetto di estensione in quel momento.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-154">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
 <span data-ttu-id="3b9ad-155">Quando un oggetto viene aggiunto, il chiamante del metodo <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> deve essere completamente attendibile secondo il criterio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-155">When an object is added, the caller of the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> must be fully trusted in the security policy.</span></span> <span data-ttu-id="3b9ad-156">Se il chiamante è di tipo semi-trusted, l'aggiunta avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-156">If the caller is semi-trusted, the addition will fail.</span></span>  
  
 <span data-ttu-id="3b9ad-157">Anche se un oggetto viene aggiunto correttamente, questo non significa che l'esecuzione avverrà correttamente.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-157">Though an object is added successfully, it does not guarantee that the execution will be successful.</span></span> <span data-ttu-id="3b9ad-158">Quando viene chiamato il metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, le autorizzazioni vengono calcolate in base all'evidenza fornita nella fase <xref:System.Xml.Xsl.XslTransform.Load%2A> e il set di autorizzazioni viene assegnato all'intero processo di trasformazione.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-158">When the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is called, permissions are calculated against the evidence provided at <xref:System.Xml.Xsl.XslTransform.Load%2A> time, and that permission set is assigned to the entire transformation process.</span></span> <span data-ttu-id="3b9ad-159">Se un oggetto di estensione tenta di avviare un'azione che necessita di autorizzazioni non presenti nel set, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-159">If an extension object attempts to initiate an action that requires permissions not found in the set, an exception is thrown.</span></span>  
  
 <span data-ttu-id="3b9ad-160">Dagli oggetti di estensione vengono restituiti dati appartenenti a uno dei quattro tipi di dati XPath principali, e cioè number, string, boolean o node set.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-160">The data types returned from extension objects are one of the four basic XPath data types of number, string, Boolean, and node set.</span></span>  
  
#### <a name="to-use-the-xslt-extension-object-the-user-needs-to-do-the-following"></a><span data-ttu-id="3b9ad-161">Per usare l'oggetto di estensione XSLT, è necessario:</span><span class="sxs-lookup"><span data-stu-id="3b9ad-161">To use the XSLT extension object, the user needs to do the following:</span></span>  
  
1.  <span data-ttu-id="3b9ad-162">Creare un <xref:System.Xml.Xsl.XsltArgumentList> e aggiungere l'oggetto di estensione usando <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-162">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span></span>  
  
2.  <span data-ttu-id="3b9ad-163">Richiamare l'oggetto di estensione dal foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-163">Invoke the extension object from the style sheet.</span></span>  
  
3.  <span data-ttu-id="3b9ad-164">Passare l'oggetto <xref:System.Xml.Xsl.XsltArgumentList> al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> .</span><span class="sxs-lookup"><span data-stu-id="3b9ad-164">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="3b9ad-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b9ad-165">Example</span></span>  
 <span data-ttu-id="3b9ad-166">Nell'esempio seguente viene calcolata la circonferenza di un cerchio di cui viene fornito il raggio.</span><span class="sxs-lookup"><span data-stu-id="3b9ad-166">The following example calculates the circumference of a circle given its radius.</span></span>  
  
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
  public class Calculate{  
  
    private double circ = 0;  
  
    public double Circumference(double radius){  
       circ = Math.PI*2*radius;  
       return circ;  
    }  
  }  
}  
```  
  
### <a name="input"></a><span data-ttu-id="3b9ad-167">Input</span><span class="sxs-lookup"><span data-stu-id="3b9ad-167">Input</span></span>  
 <span data-ttu-id="3b9ad-168">number.xml</span><span class="sxs-lookup"><span data-stu-id="3b9ad-168">number.xml</span></span>  
  
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
  
 <span data-ttu-id="3b9ad-169">circle.xsl</span><span class="sxs-lookup"><span data-stu-id="3b9ad-169">circle.xsl</span></span>  
  
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
  
### <a name="output"></a><span data-ttu-id="3b9ad-170">Output</span><span class="sxs-lookup"><span data-stu-id="3b9ad-170">Output</span></span>  
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
  
## <a name="see-also"></a><span data-ttu-id="3b9ad-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b9ad-171">See Also</span></span>  
 [<span data-ttu-id="3b9ad-172">Classe XslTransform implementa il processore XSLT</span><span class="sxs-lookup"><span data-stu-id="3b9ad-172">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
