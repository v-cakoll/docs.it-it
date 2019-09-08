---
title: Applicazione di una trasformazione XSLT a un DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: d9767844400d67e81c7065148b22c62352af0428
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784792"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a>Applicazione di una trasformazione XSLT a un DataSet
Il metodo **WriteXml** di <xref:System.Data.DataSet> consente di scrivere il contenuto di un **DataSet** come dati XML. Tali dati XML vengono solitamente convertiti in un formato diverso mediante XSLT (Extensible Stylesheets Language Transformations). Tuttavia, la sincronizzazione di un **DataSet** con <xref:System.Xml.XmlDataDocument> un oggetto consente di applicare un foglio di stile XSLT al contenuto di un **DataSet** senza dover prima scrivere il contenuto del **DataSet** come dati XML tramite **WriteXml**.  
  
 Nell'esempio seguente viene compilato un **set** di dati con tabelle e relazioni, viene sincronizzato il **set di dati** con un **XmlDataDocument**e viene scritta una parte del **set di dati** come file HTML utilizzando un foglio di stile XSLT. Di seguito viene riportato il contenuto del foglio di stile XSLT.  
  
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
  
 Il codice seguente compila il **set di dati** e applica il foglio di stile XSLT.  
  
> [!NOTE]
> Se si applica un foglio di stile XSLT a un **set di dati** che contiene relazioni, si ottengono prestazioni ottimali se si imposta la <xref:System.Data.DataRelation> proprietà **Nested** di su **true** per ogni relazione annidata. Ciò consente di navigare all'interno della gerarchia e trasformare i dati mediante i fogli di stile XSLT, che implementano un'elaborazione sequenziale dall'alto verso il basso, anziché mediante gli assi di posizione XPath, ad esempio i nodi di pari livello precedenti e successivi nelle espressioni di verifica del nodo dei fogli di stile, che comportano un maggiore dispendio di risorse. Per ulteriori informazioni sulle relazioni annidate, vedere [nidificazione di oggetti DataRelation](nesting-datarelations.md).  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Sincronizzazione di DataSet e XmlDataDocument](dataset-and-xmldatadocument-synchronization.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
