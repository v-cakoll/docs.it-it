---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151169"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Derivazione della struttura relazionale di dataset da XML Schema (XSD)
Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language). In generale, `complexType` per ogni elemento figlio di un elemento `DataSet`dello schema, viene generata una tabella nell'oggetto . La struttura della tabella è determinata dalla definizione del tipo complesso. Le tabelle vengono `DataSet` create negli elementi di primo livello per lo schema. Tuttavia, una tabella viene creata `complexType` solo per `complexType` un elemento `complexType` di primo livello quando `complexType` l'elemento è `DataTable` annidato all'interno di un altro elemento, nel qual caso l'elemento nidificato viene mappato a un all'interno di `DataSet`.  
  
 Per ulteriori informazioni su XSD, vedere la parte 0 della sezione Schema XML del World Wide Web Consortium (W3C) [, Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/)e XML Schema Part [2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).  
  
 Nell'esempio seguente viene `customers` illustrato uno schema `MyDataSet` XML in cui è l'elemento figlio dell'elemento, che è un **DataSet** elemento.  
  
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
> Se l'elemento `customers` è di un tipo di dati Schema XML semplice, ad esempio **integer**, non viene generata alcuna tabella. Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.  
  
 Nello schema XML seguente l'elemento **Schema** `InStateCustomers` ha `OutOfStateCustomers`due elementi figlio e .  
  
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
  
 Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`). Di conseguenza, il processo di mapping `DataSet`genera le due tabelle identiche seguenti nel file .  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di dataset](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi dello schema XML utilizzati `DataSet`per creare vincoli di chiave univoca ed esterna in un oggetto .  
  
 [Generazione di relazioni tra dataset da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Vengono descritti gli elementi dello schema XML utilizzati per creare relazioni tra le colonne della tabella in un `DataSet`oggetto .  
  
 [Vincoli e relazioni di XML Schema](xml-schema-constraints-and-relationships.md)  
 Viene descritto come le relazioni vengono create in modo `DataSet`implicito quando si utilizzano gli elementi xml Schema per creare vincoli in un oggetto .  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Utilizzo di XML in un dataset](using-xml-in-a-dataset.md)  
 Viene descritto come caricare e rendere persistente `DataSet` la struttura relazionale e i dati in un database XML.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../ado-net-overview.md)
