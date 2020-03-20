---
title: Sincronizzazione di un dataset con un oggetto XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fbc96fa9-b5d1-4f97-b099-c89b0e14ce2c
ms.openlocfilehash: 2ee5b0937f24fac745f72cf6ef6e4bef9ec97ba8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150781"
---
# <a name="synchronizing-a-dataset-with-an-xmldatadocument"></a><span data-ttu-id="15d41-102">Sincronizzazione di un dataset con un oggetto XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="15d41-102">Synchronizing a DataSet with an XmlDataDocument</span></span>
<span data-ttu-id="15d41-103">Contenuto della sezione viene descritto un passaggio dell'elaborazione di un ordine di acquisto mediante un <xref:System.Data.DataSet> fortemente tipizzato e sincronizzato con un <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="15d41-103">This section demonstrates one step in the processing of a purchase order, using a strongly typed <xref:System.Data.DataSet> synchronized with an <xref:System.Xml.XmlDataDocument>.</span></span> <span data-ttu-id="15d41-104">Gli esempi che seguono creano un **DataSet** con uno schema ridotto a icona che corrisponde solo a una parte del documento XML di origine.</span><span class="sxs-lookup"><span data-stu-id="15d41-104">The examples that follow create a **DataSet** with a minimized schema that matches only a portion of the source XML document.</span></span> <span data-ttu-id="15d41-105">Negli esempi viene utilizzato un **XmlDataDocument** per mantenere la fedeltà del documento XML di origine, consentendo l'utilizzo del **DataSet** per esporre un sottoinsieme del documento XML.</span><span class="sxs-lookup"><span data-stu-id="15d41-105">The examples use an **XmlDataDocument** to preserve the fidelity of the source XML document, enabling the **DataSet** to be used to expose a subset of the XML document.</span></span>  
  
 <span data-ttu-id="15d41-106">Nel seguente documento XML sono contenute tutte le informazioni relative a un ordine di acquisto: informazioni relative al cliente, articoli ordinati, informazioni sulla spedizione e così via.</span><span class="sxs-lookup"><span data-stu-id="15d41-106">The following XML document contains all the information pertaining to a purchase order: customer information, items ordered, shipping information, and so on.</span></span>  
  
```xml  
<?xml version="1.0" standalone="yes"?>  
<PurchaseOrder>  
  <Customers>  
    <CustomerID>CHOPS</CustomerID>  
    <Orders>  
      <OrderID>10966</OrderID>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>37</ProductID>  
        <UnitPrice>26</UnitPrice>  
        <Quantity>8</Quantity>  
        <Discount>0</Discount>  
      </OrderDetails>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>56</ProductID>  
        <UnitPrice>38</UnitPrice>  
        <Quantity>12</Quantity>  
        <Discount>0.15</Discount>  
      </OrderDetails>  
      <OrderDetails>  
        <OrderID>10966</OrderID>  
        <ProductID>62</ProductID>  
        <UnitPrice>49.3</UnitPrice>  
        <Quantity>12</Quantity>  
        <Discount>0.15</Discount>  
      </OrderDetails>  
      <CustomerID>CHOPS</CustomerID>  
      <EmployeeID>4</EmployeeID>  
      <OrderDate>1998-03-20T00:00:00.0000000</OrderDate>  
      <RequiredDate>1998-04-17T00:00:00.0000000</RequiredDate>  
      <ShippedDate>1998-04-08T00:00:00.0000000</ShippedDate>  
      <ShipVia>1</ShipVia>  
      <Freight>27.19</Freight>  
      <ShipName>Chop-suey Chinese</ShipName>  
      <ShipAddress>Hauptstr. 31</ShipAddress>  
      <ShipCity>Bern</ShipCity>  
      <ShipPostalCode>3012</ShipPostalCode>  
      <ShipCountry>Switzerland</ShipCountry>  
    </Orders>  
    <CompanyName>Chop-suey Chinese</CompanyName>  
    <ContactName>Yang Wang</ContactName>  
    <ContactTitle>Owner</ContactTitle>  
    <Address>Hauptstr. 29</Address>  
    <City>Bern</City>  
    <PostalCode>3012</PostalCode>  
    <Country>Switzerland</Country>  
    <Phone>0452-076545</Phone>  
  </Customers>  
  <Shippers>  
    <ShipperID>1</ShipperID>  
    <CompanyName>Speedy Express</CompanyName>  
    <Phone>(503) 555-0100</Phone>  
  </Shippers>  
  <Shippers>  
    <ShipperID>2</ShipperID>  
    <CompanyName>United Package</CompanyName>  
    <Phone>(503) 555-0101</Phone>  
  </Shippers>  
  <Shippers>  
    <ShipperID>3</ShipperID>  
    <CompanyName>Federal Shipping</CompanyName>  
    <Phone>(503) 555-0102</Phone>  
  </Shippers>  
  <Products>  
    <ProductID>37</ProductID>  
    <ProductName>Gravad lax</ProductName>  
    <QuantityPerUnit>12 - 500 g pkgs.</QuantityPerUnit>  
    <UnitsInStock>11</UnitsInStock>  
    <UnitsOnOrder>50</UnitsOnOrder>  
    <ReorderLevel>25</ReorderLevel>  
  </Products>  
  <Products>  
    <ProductID>56</ProductID>  
    <ProductName>Gnocchi di nonna Alice</ProductName>  
    <QuantityPerUnit>24 - 250 g pkgs.</QuantityPerUnit>  
    <UnitsInStock>21</UnitsInStock>  
    <UnitsOnOrder>10</UnitsOnOrder>  
    <ReorderLevel>30</ReorderLevel>  
  </Products>  
  <Products>  
    <ProductID>62</ProductID>  
    <ProductName>Tarte au sucre</ProductName>  
    <QuantityPerUnit>48 pies</QuantityPerUnit>  
    <UnitsInStock>17</UnitsInStock>  
    <UnitsOnOrder>0</UnitsOnOrder>  
    <ReorderLevel>0</ReorderLevel>  
  </Products>  
</PurchaseOrder>  
```  
  
 <span data-ttu-id="15d41-107">Uno dei passaggi dell'elaborazione delle informazioni relative all'ordine di acquisto contenuto nel documento XML precedente consiste nella compilazione dell'ordine dall'inventario corrente della società.</span><span class="sxs-lookup"><span data-stu-id="15d41-107">One step in processing the purchase order information contained in the preceding XML document is for the order to be filled from the company's current inventory.</span></span> <span data-ttu-id="15d41-108">Non è necessario che l'intero contenuto dell'ordine di acquisto sia visibile al dipendente responsabile della compilazione dell'ordine dal magazzino della società; è necessario che siano visibili solo le informazioni relative all'ordine.</span><span class="sxs-lookup"><span data-stu-id="15d41-108">The employee responsible for filling the order from the company's warehouse does not need to see the entire contents of the purchase order; they only need to see the product information for the order.</span></span> <span data-ttu-id="15d41-109">Per esporre solo le informazioni sul prodotto dal documento XML, creare un **DataSet** fortemente tipizzato con uno schema, scritto come schema XSD (XML Schema Definition Language), che esegue il mapping ai prodotti e alle quantità ordinate.</span><span class="sxs-lookup"><span data-stu-id="15d41-109">To expose only the product information from the XML document, create a strongly typed **DataSet** with a schema, written as XML Schema definition language (XSD) schema, that maps to the products and quantities ordered.</span></span> <span data-ttu-id="15d41-110">Per ulteriori informazioni sugli oggetti **DataSet** fortemente tipizzati, vedere [Set di dati tipizzati](typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="15d41-110">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="15d41-111">Nel codice seguente viene illustrato lo schema da cui viene generato il **DataSet** fortemente tipizzato per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="15d41-111">The following code shows the schema from which the strongly typed **DataSet** is generated for this sample.</span></span>  
  
```xml  
<?xml version="1.0" standalone="yes"?>  
<xs:schema id="OrderDetail" xmlns=""
                            xmlns:xs="http://www.w3.org/2001/XMLSchema"
                            xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"
                            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="OrderDetail" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetails" codegen:typedName="LineItem" codegen:typedPlural="LineItems">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" type="xs:int" minOccurs="0" codegen:typedName="OrderID"/>  
              <xs:element name="Quantity" type="xs:short" minOccurs="0" codegen:typedName="Quantity"/>  
              <xs:element name="ProductID" type="xs:int" minOccurs="0" codegen:typedName="ProductID"/>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Products" codegen:typedName="Product" codegen:typedPlural="Products">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="ProductID" type="xs:int" minOccurs="0" codegen:typedName="ProductID"/>  
              <xs:element name="ProductName" type="xs:string" minOccurs="0" codegen:typedName="ProductName"/>  
              <xs:element name="QuantityPerUnit" type="xs:string" minOccurs="0" codegen:typedName="QuantityPerUnit"/>  
              <xs:element name="UnitsInStock" type="xs:short" minOccurs="0" codegen:typedName="UnitsInStock"/>  
              <xs:element name="UnitsOnOrder" type="xs:short" minOccurs="0" codegen:typedName="UnitsOnOrder"/>  
              <xs:element name="ReorderLevel" type="xs:short" minOccurs="0" codegen:typedName="ReorderLevel"/>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Products" />  
      <xs:field xpath="ProductID" />  
    </xs:unique>  
    <xs:keyref name="Relation1" refer="Constraint1" codegen:typedChildren="GetLineItems" codegen:typedParent="Product">  
      <xs:selector xpath=".//OrderDetails" />  
      <xs:field xpath="ProductID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="15d41-112">Si noti che solo le informazioni contenute negli elementi **OrderDetails** e **Products** del documento XML originale sono incluse nello schema per il **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="15d41-112">Notice that only information from the **OrderDetails** and **Products** elements of the original XML document are included in the schema for the **DataSet**.</span></span> <span data-ttu-id="15d41-113">La sincronizzazione del **DataSet** con un **XmlDataDocument** garantisce che gli elementi non inclusi nel **DataSet** verranno mantenuti con il documento XML.</span><span class="sxs-lookup"><span data-stu-id="15d41-113">Synchronizing the **DataSet** with an **XmlDataDocument** ensures that the elements not included in the **DataSet** will persist with the XML document.</span></span>  
  
 <span data-ttu-id="15d41-114">Con il **DataSet** fortemente tipizzato generato dallo schema XML (con uno spazio dei nomi **Northwind.FillOrder**), è possibile esporre una parte del documento XML originale sincronizzando il **DataSet** con l'XmlDataDocument caricato dal documento XML di origine. **XmlDataDocument**</span><span class="sxs-lookup"><span data-stu-id="15d41-114">With the strongly typed **DataSet** generated from the XML Schema (with a namespace of **Northwind.FillOrder**), a portion of the original XML document can be exposed by synchronizing the **DataSet** with the **XmlDataDocument** loaded from the source XML document.</span></span> <span data-ttu-id="15d41-115">Si noti che il **DataSet** generato dallo schema contiene struttura ma non dati.</span><span class="sxs-lookup"><span data-stu-id="15d41-115">Notice that the **DataSet** generated from the schema contains structure but no data.</span></span> <span data-ttu-id="15d41-116">I dati vengono compilati quando si carica il codice XML in **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="15d41-116">The data is filled in when you load the XML into the **XmlDataDocument**.</span></span> <span data-ttu-id="15d41-117">Se si tenta di caricare un **XmlDataDocument** sincronizzato con un **DataSet** che contiene già dati, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="15d41-117">If you attempt to load an **XmlDataDocument** that has been synchronized with a **DataSet** that already contains data, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="15d41-118">Dopo l'aggiornamento del **DataSet** (e **XmlDataDocument**), **xmlDataDocument** può scrivere il documento XML modificato con gli elementi ignorati dal **DataSet** ancora intatti, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="15d41-118">After the **DataSet** (and the **XmlDataDocument**) has been updated, the **XmlDataDocument** can then write out the modified XML document with the elements ignored by the **DataSet** still intact, as shown below.</span></span> <span data-ttu-id="15d41-119">Nello scenario relativo all'ordine di acquisto, dopo l'inserimento degli articoli ordinati, è possibile passare il documento XML al passaggio successivo del processo dell'ordine di acquisto, ad esempio al reparto spedizioni della società.</span><span class="sxs-lookup"><span data-stu-id="15d41-119">In the purchase order scenario, after the order items have been filled, the modified XML document can then be passed on to the next step in the order process, perhaps to the company's shipping department.</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Xml  
Imports Northwind.FillOrder  
  
Public class Sample  
  Public Shared Sub Main()  
  
    Dim orderDS As OrderDetail = New OrderDetail  
  
    Dim xmlDocument As XmlDataDocument = New XmlDataDocument(orderDS)
  
    xmlDocument.Load("Order.xml")  
  
    Dim orderItem As OrderDetail.LineItem  
    Dim product As OrderDetail.Product  
  
    For Each orderItem In orderDS.LineItems  
      product = orderItem.Product  
  
      ' Remove quantity from the current stock.  
      product.UnitsInStock = CType(product.UnitsInStock - orderItem.Quantity, Short)  
  
      ' If the remaining stock is less than the reorder level, order more.  
      If ((product.UnitsInStock + product.UnitsOnOrder) < product.ReorderLevel) Then  
        product.UnitsOnOrder = CType(product.UnitsOnOrder + product.ReorderLevel, Short)  
      End If  
    Next  
  
    xmlDocument.Save("Order_out.xml")  
  End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Xml;  
using Northwind.FillOrder;  
  
public class Sample  
{  
  public static void Main()  
  {  
    OrderDetail orderDS = new OrderDetail();
  
    XmlDataDocument xmlDocument = new XmlDataDocument(orderDS);
  
    xmlDocument.Load("Order.xml");  
  
    foreach (OrderDetail.LineItem orderItem in orderDS.LineItems)  
    {  
      OrderDetail.Product product = orderItem.Product;  
  
      // Remove quantity from the current stock.  
      product.UnitsInStock = (short)(product.UnitsInStock - orderItem.Quantity);  
  
      // If the remaining stock is less than the reorder level, order more.  
      if ((product.UnitsInStock + product.UnitsOnOrder) < product.ReorderLevel)  
        product.UnitsOnOrder = (short)(product.UnitsOnOrder + product.ReorderLevel);  
    }  
  
    xmlDocument.Save("Order_out.xml");  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="15d41-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15d41-120">See also</span></span>

- [<span data-ttu-id="15d41-121">Sincronizzazione di DataSet e XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="15d41-121">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="15d41-122">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="15d41-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
