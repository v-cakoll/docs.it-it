---
title: Deduzione di tabelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2c00dd11d4d93e5d3b0e2f1c3b75765056a10cab
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-tables"></a>Deduzione di tabelle
Durante l'inferenza di uno schema per un tipo <xref:System.Data.DataSet> da un documento XML, ADO.NET determina innanzitutto quali elementi XML rappresentano tabelle. Le seguenti strutture XML come risultato una tabella per la **DataSet** schema:  
  
-   Elementi con attributi  
  
-   Elementi con elementi figlio  
  
-   Elementi ripetuti  
  
## <a name="elements-with-attributes"></a>Elementi con attributi  
 Gli elementi in cui sono stati specificati degli attributi daranno come risultato delle tabelle inferite. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza produce una tabella denominata "Element1".  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## <a name="elements-with-child-elements"></a>Elementi con elementi figlio  
 Gli elementi a cui sono associati elementi figlio daranno come risultato delle tabelle inferite. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza produce una tabella denominata "Element1".  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 L'elemento del documento, o elemento radice, dà come risultato una tabella inferita nel caso in cui a tale elemento siano associati attributi o elementi figlio che vengono inferiti come colonne. Se l'elemento del documento dispone di alcun attributo e non gli elementi figlio da inferire come colonne, l'elemento viene inferito come un **DataSet**. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 Il processo di inferenza produce una tabella denominata "DocumentElement".  
  
 **Set di dati:** NewDataSet  
  
 **Tabella:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 Si consideri in alternativa il seguente elemento XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Il processo di inferenza produce una **DataSet** denominato "DocumentElement" contenente una tabella denominata "Element1".  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="repeating-elements"></a>Elementi ripetuti  
 Gli elementi ripetuti danno come risultato una singola tabella inferita. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza produce una tabella denominata "Element1".  
  
 **Set di dati:** DocumentElement  
  
 **Tabella:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## <a name="see-also"></a>Vedere anche  
 [Deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Caricamento delle informazioni dello schema DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
