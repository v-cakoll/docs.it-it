---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 549579fca0179994191987097c12b6085ee91756
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119691"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Derivazione della struttura relazionale di dataset da XML Schema (XSD)
Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language). In generale, per ognuno `complexType` nell'elemento figlio di un elemento dello schema, viene generata una tabella di `DataSet`. La struttura della tabella è determinata dalla definizione del tipo complesso. Le tabelle vengono create nel `DataSet` per gli elementi di primo livello nello schema. Tuttavia, una tabella viene creata solo per un livello superiore `complexType` elemento quando il `complexType` è annidato all'interno di un altro elemento `complexType` elemento, nel quale caso annidata `complexType` elemento viene mappato a una `DataTable` all'interno del `DataSet`.  
  
 Per altre informazioni su XSD, vedere il World Wide Web Consortium (W3C) [XML Schema Part 0: Introduzione alla raccomandazione](https://www.w3.org/TR/xmlschema-0/), il [XML Schema Part 1: Strutture di raccomandazione](https://www.w3.org/TR/xmlschema-1/)e il [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).  
  
 Nell'esempio seguente viene illustrato un XML Schema in cui `customers` è l'elemento figlio del `MyDataSet` elemento, che è un **DataSet** elemento.  
  
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
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 Il tipo di dati relativo a ogni colonna della tabella viene derivato dal tipo di XML Schema relativo al corrispondente elemento o attributo specificato.  
  
> [!NOTE]
>  Se l'elemento `customers` è un tipo di dati XML Schema semplice, ad esempio **integer**, verrà generata alcuna tabella. Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.  
  
 Nello Schema XML seguente, il **Schema** elemento ha due figli, `InStateCustomers` e `OutOfStateCustomers`.  
  
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
  
 Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`). Pertanto, il processo di mapping che genera l'errore di due tabelle identiche seguenti nel `DataSet`.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di dataset](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare i vincoli di chiave univoci ed esterni in un `DataSet`.  
  
 [Generazione di relazioni tra dataset da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Vengono descritti gli elementi di XML Schema usati per creare relazioni tra le colonne della tabella in un `DataSet`.  
  
 [Vincoli e relazioni di XML Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 Viene descritto come le relazioni vengono create in modo implicito quando si usano elementi di XML Schema per creare vincoli in un `DataSet`.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Utilizzo di XML in un dataset](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Viene descritto come caricare e mantenere la struttura relazionale e i dati in un `DataSet` come dati XML.  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
