---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: eb4f6e3a63c901ec69ca5572a6f79d2f0ac4adfc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Derivazione della struttura relazionale di dataset da XML Schema (XSD)
Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language). In generale, per ogni `complexType` elemento figlio di un elemento dello schema, in cui viene generata una tabella di `DataSet`. La struttura della tabella è determinata dalla definizione del tipo complesso. Le tabelle vengono create nel `DataSet` per gli elementi di primo livello nello schema. Tuttavia, una tabella viene creata solo per un livello superiore `complexType` elemento quando il `complexType` è annidato l'elemento all'interno di un altro `complexType` elemento, in cui caso nidificata `complexType` elemento viene mappato a un `DataTable` all'interno del `DataSet`.  
  
 Per ulteriori informazioni su XSD, vedere il World Wide Web Consortium (W3C) XML Schema Part 0: Primer raccomandazione, XML Schema Part 1: Structures Recommendation e XML Schema Part 2: Datatypes Recommendation, disponibile all'indirizzo [http:// www.w3.org/](http://www.w3.org/TR/).  
  
 Nell'esempio seguente viene illustrato un XML Schema in cui `customers` è l'elemento figlio del `MyDataSet` elemento, ovvero un **DataSet** elemento.  
  
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
>  Se l'elemento `customers` è di un tipo di dati XML Schema semplice, ad esempio **intero**, verrà generata alcuna tabella. Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.  
  
 Nello Schema XML seguente, il **Schema** elemento dispone di due elementi figlio, `InStateCustomers` e `OutOfStateCustomers`.  
  
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
  
 Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`). Pertanto, il processo di mapping genera le due tabelle identiche seguenti nel `DataSet`.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>In questa sezione  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli di chiave esterni e univoci in un `DataSet`.  
  
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne della tabella in un `DataSet`.  
  
 [Vincoli e relazioni di XML Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 Viene descritto come le relazioni vengono create in modo implicito quando si usano elementi di XML Schema per creare vincoli in un `DataSet`.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Viene descritto come caricare e mantenere la struttura relazionale e i dati in un `DataSet` come dati XML.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
