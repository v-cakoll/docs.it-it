---
title: Deduzione di tabelle
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 52ffd3fe90eb491dd01acf8538276cc828fdb309
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784489"
---
# <a name="inferring-tables"></a>Deduzione di tabelle
Durante l'inferenza di uno schema per un tipo <xref:System.Data.DataSet> da un documento XML, ADO.NET determina innanzitutto quali elementi XML rappresentano tabelle. Le strutture XML seguenti generano una tabella per lo schema del **set di dati** :  
  
- Elementi con attributi  
  
- Elementi con elementi figlio  
  
- Elementi ripetuti  
  
## <a name="elements-with-attributes"></a>Elementi con attributi  
 Gli elementi in cui sono stati specificati degli attributi daranno come risultato delle tabelle inferite. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 Il processo di inferenza produce una tabella denominata "Element1".  
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
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
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 L'elemento del documento, o elemento radice, dà come risultato una tabella inferita nel caso in cui a tale elemento siano associati attributi o elementi figlio che vengono inferiti come colonne. Se l'elemento del documento non ha attributi e nessun elemento figlio da inferire come colonne, l'elemento viene dedotto come un set di **dati**. Ad esempio, si consideri il seguente codice XML:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 Il processo di inferenza produce una tabella denominata "DocumentElement".  
  
 **DataSet** NewDataSet  
  
 **tavolo:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 Si consideri in alternativa il seguente elemento XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Il processo di inferenza produce un **set di dati** denominato "DocumentElement" contenente una tabella denominata "Element1".  
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
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
  
 **DataSet** DocumentElement  
  
 **tavolo:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## <a name="see-also"></a>Vedere anche

- [Deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un oggetto DataSet da XML](loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](loading-dataset-schema-information-from-xml.md)
- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
