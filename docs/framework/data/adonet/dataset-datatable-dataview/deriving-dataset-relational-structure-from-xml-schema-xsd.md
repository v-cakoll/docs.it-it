---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: ef77030b4e847f91fea074b68e223ac622539048
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040096"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Derivazione della struttura relazionale di dataset da XML Schema (XSD)
Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language). In generale, per ogni `complexType` elemento figlio di un elemento dello schema, viene generata una tabella nel `DataSet`. La struttura della tabella è determinata dalla definizione del tipo complesso. Le tabelle vengono create nel `DataSet` per gli elementi di livello superiore nello schema. Tuttavia, una tabella viene creata solo per un elemento `complexType` di primo livello quando l'elemento `complexType` è annidato all'interno di un altro elemento `complexType`, nel qual caso l'elemento `complexType` annidato viene mappato a un `DataTable` all'interno dell'`DataSet`.  
  
 Per ulteriori informazioni su XSD, vedere la raccomandazione World Wide Web Consortium (W3C) [XML Schema Part 0:](https://www.w3.org/TR/xmlschema-0/)nozioni di fondo, la raccomandazione [XML Schema Part 1: Structures](https://www.w3.org/TR/xmlschema-1/)e la [raccomandazione XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/).  
  
 Nell'esempio seguente viene illustrato uno schema XML in cui `customers` è l'elemento figlio dell'elemento `MyDataSet`, che è un elemento del **set di dati** .  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 L'elemento `customers` nell'esempio precedente è un elemento di tipo complesso. La definizione di tipo complesso viene quindi analizzata e la tabella seguente viene creata dal processo di mapping.  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Il tipo di dati relativo a ogni colonna della tabella viene derivato dal tipo di XML Schema relativo al corrispondente elemento o attributo specificato.  
  
> [!NOTE]
> Se l'elemento `customers` è di un tipo di dati XML Schema semplice, ad esempio **Integer**, non viene generata alcuna tabella. Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.  
  
 Nell'XML schema seguente l'elemento **schema** ha due elementi figlio, `InStateCustomers` e `OutOfStateCustomers`.  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`). Pertanto, il processo di mapping genera le due tabelle identiche seguenti nell'`DataSet`.  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli UNIQUE ed Foreign Key in un `DataSet`.  
  
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne della tabella in un `DataSet`.  
  
 [Vincoli e relazioni di XML Schema](xml-schema-constraints-and-relationships.md)  
 Viene descritto come vengono create le relazioni in modo implicito quando si utilizzano gli elementi dello schema XML per creare vincoli in una `DataSet`.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Uso di XML in un set di dati](using-xml-in-a-dataset.md)  
 Viene descritto come caricare e salvare in modo permanente la struttura relazionale e i dati in un `DataSet` come dati XML.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../ado-net-overview.md)
