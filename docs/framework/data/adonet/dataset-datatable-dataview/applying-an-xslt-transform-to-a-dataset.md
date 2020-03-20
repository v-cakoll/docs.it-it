---
title: Applicazione di una trasformazione XSLT a un DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: 3f066f29b99ade6e92a263110fed8079208567b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151494"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a><span data-ttu-id="63428-102">Applicazione di una trasformazione XSLT a un DataSet</span><span class="sxs-lookup"><span data-stu-id="63428-102">Applying an XSLT Transform to a DataSet</span></span>

<span data-ttu-id="63428-103">Il **metodo WriteXml** dell'oggetto <xref:System.Data.DataSet> consente di scrivere il contenuto di un **DataSet** come dati XML.</span><span class="sxs-lookup"><span data-stu-id="63428-103">The **WriteXml** method of the <xref:System.Data.DataSet> enables you to write the contents of a **DataSet** as XML data.</span></span> <span data-ttu-id="63428-104">Tali dati XML vengono solitamente convertiti in un formato diverso mediante XSLT (Extensible Stylesheets Language Transformations).</span><span class="sxs-lookup"><span data-stu-id="63428-104">A common task is to then transform that XML to another format using XSL transformations (XSLT).</span></span> <span data-ttu-id="63428-105">Tuttavia, la sincronizzazione <xref:System.Xml.XmlDataDocument> di un **DataSet** con un consente di applicare un foglio di stile XSLT al contenuto di un **DataSet** senza dover prima scrivere il contenuto del **DataSet** come dati XML utilizzando **WriteXml**.</span><span class="sxs-lookup"><span data-stu-id="63428-105">However, synchronizing a **DataSet** with an <xref:System.Xml.XmlDataDocument> enables you to apply an XSLT stylesheet to the contents of a **DataSet** without having to first write the contents of the **DataSet** as XML data using **WriteXml**.</span></span>  
  
 <span data-ttu-id="63428-106">Nell'esempio seguente viene popolato un **DataSet** con tabelle e relazioni, viene sincronizzato il **DataSet** con un **xmlDataDocument**e viene scritto una parte del **DataSet** come file HTML utilizzando un foglio di stile XSLT.</span><span class="sxs-lookup"><span data-stu-id="63428-106">The following example populates a **DataSet** with tables and relationships, synchronizes the **DataSet** with an **XmlDataDocument**, and writes a portion of the **DataSet** as an HTML file using an XSLT stylesheet.</span></span> <span data-ttu-id="63428-107">Di seguito è riportato il contenuto del foglio di stile XSLT:</span><span class="sxs-lookup"><span data-stu-id="63428-107">The following are the contents of the XSLT stylesheet:</span></span>
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
<xsl:template match="CustomerOrders">  
  <HTML>  
  <STYLE>  
  BODY {font-family:verdana;font-size:9pt}  
  TD   {font-size:8pt}  
  </STYLE>  
    <BODY>  
    <TABLE BORDER="1">  
      <xsl:apply-templates select="Customers"/>  
    </TABLE>  
    </BODY>  
  </HTML>  
</xsl:template>  
  
<xsl:template match="Customers">  
    <TR><TD>  
      <xsl:value-of select="ContactName"/>, <xsl:value-of select="Phone"/><BR/>  
    </TD></TR>  
      <xsl:apply-templates select="Orders"/>  
</xsl:template>  
  
<xsl:template match="Orders">  
  <TABLE BORDER="1">  
    <TR><TD valign="top"><B>Order:</B></TD><TD valign="top"><xsl:value-of select="OrderID"/></TD></TR>  
    <TR><TD valign="top"><B>Date:</B></TD><TD valign="top"><xsl:value-of select="OrderDate"/></TD></TR>  
    <TR><TD valign="top"><B>Ship To:</B></TD>  
        <TD valign="top"><xsl:value-of select="ShipName"/><BR/>  
        <xsl:value-of select="ShipAddress"/><BR/>  
        <xsl:value-of select="ShipCity"/>, <xsl:value-of select="ShipRegion"/>  <xsl:value-of select="ShipPostalCode"/><BR/>  
        <xsl:value-of select="ShipCountry"/></TD></TR>  
  </TABLE>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="63428-108">Il codice seguente riempie il **DataSet** e applica il foglio di stile XSLT.</span><span class="sxs-lookup"><span data-stu-id="63428-108">The following code fills the **DataSet** and applies the XSLT style sheet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63428-109">Se si applica un foglio di stile XSLT a un **DataSet** che **Nested** contiene relazioni, <xref:System.Data.DataRelation> è possibile ottenere prestazioni ottimali se si imposta la proprietà Nested di **su true** per ogni relazione nidificata.</span><span class="sxs-lookup"><span data-stu-id="63428-109">If you are applying an XSLT style sheet to a **DataSet** that contains relations, you achieve best performance if you set the **Nested** property of the <xref:System.Data.DataRelation> to **true** for each nested relation.</span></span> <span data-ttu-id="63428-110">Ciò consente di navigare all'interno della gerarchia e trasformare i dati mediante i fogli di stile XSLT, che implementano un'elaborazione sequenziale dall'alto verso il basso, anziché mediante gli assi di posizione XPath, ad esempio i nodi di pari livello precedenti e successivi nelle espressioni di verifica del nodo dei fogli di stile, che comportano un maggiore dispendio di risorse.</span><span class="sxs-lookup"><span data-stu-id="63428-110">This allows you to use XSLT style sheets that implement natural top-down processing to navigate the hierarchy and transform the data, as opposed to using performance-intensive XPath location axes (for example, preceding-sibling and following-sibling in style sheet node test expressions) to navigate it.</span></span> <span data-ttu-id="63428-111">Per ulteriori informazioni sulle relazioni nidificate, consultate [Nidificazione di DataRelations.](nesting-datarelations.md)</span><span class="sxs-lookup"><span data-stu-id="63428-111">For more information on nested relations, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)
  
Dim xslTran As XslTransform = New XslTransform  
xslTran.Load("transform.xsl")  
  
Dim writer As XmlTextWriter = New XmlTextWriter( _  
  "xslt_output.html", System.Text.Encoding.UTF8)  
  
xslTran.Transform(xmlDoc, Nothing, writer)  
writer.Close()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
DataSet custDS = new DataSet("CustomerDataSet");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(custDS, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(custDS, "Orders");  
  
connection.Close();  
  
custDS.Relations.Add("CustOrders",  
  custDS.Tables["Customers"].Columns["CustomerID"],  
                     custDS.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(custDS);
  
XslTransform xslTran = new XslTransform();  
xslTran.Load("transform.xsl");  
  
XmlTextWriter writer = new XmlTextWriter("xslt_output.html",
  System.Text.Encoding.UTF8);  
  
xslTran.Transform(xmlDoc, null, writer);  
writer.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="63428-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63428-112">See also</span></span>

- [<span data-ttu-id="63428-113">Sincronizzazione di DataSet e XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="63428-113">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="63428-114">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="63428-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
