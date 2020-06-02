---
title: Tipi di nodi XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
ms.openlocfilehash: 5e11d61e16659ac1a8ca1b0b2c0d493ffdad5621
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282064"
---
# <a name="types-of-xml-nodes"></a>Tipi di nodi XML
Quando un documento XML viene letto in memoria come un albero di nodi, il tipo dei nodi viene deciso al momento della creazione. Nel DOM (Document Object Model) XML sono presenti diversi tipi di nodi, determinati dal W3C (World Wide Web Consortium) ed elencati nella sezione 1.1.1 The DOM Structure Model. Nella tabella seguente vengono elencati i tipi di nodi, l'oggetto assegnato a quel tipo di nodo e una breve descrizione di ciascuno.  
  
|Tipo di nodo DOM|Oggetto|Descrizione|  
|-------------------|------------|-----------------|  
|Document|<xref:System.Xml.XmlDocument>|Contenitore di tutti i nodi dell'albero, noto anche come livello radice del documento, che non corrisponde sempre all'elemento radice.|  
|DocumentFragment|<xref:System.Xml.XmlDocumentFragment>|Contenitore temporaneo di uno o più nodi senza alcuna struttura ad albero.|  
|DocumentType|<xref:System.Xml.XmlDocumentType>|Rappresenta il nodo `<!DOCTYPE…>`.|  
|EntityReference|<xref:System.Xml.XmlEntityReference>|Rappresenta il testo di riferimento all'entità non espanso.|  
|Elemento|<xref:System.Xml.XmlElement>|Rappresenta il nodo di un elemento.|  
|Attr|<xref:System.Xml.XmlAttribute>|Rappresenta un attributo di un elemento.|  
|ProcessingInstruction|<xref:System.Xml.XmlProcessingInstruction>|Nodo di istruzioni di elaborazione.|  
|Commento|<xref:System.Xml.XmlComment>|Nodo di tipo comment.|  
|Text|<xref:System.Xml.XmlText>|Testo appartenente a un elemento o attributo.|  
|CDATASection|<xref:System.Xml.XmlCDataSection>|Rappresenta i CDATA.|  
|Entità|<xref:System.Xml.XmlEntity>|Rappresenta le dichiarazioni `<!ENTITY…>` in un documento XML, provenienti da un subset di DTD (Document Type Definition) interne o da DTD esterne ed entità dei parametri.|  
|Notation|<xref:System.Xml.XmlNotation>|Rappresenta una notazione dichiarata nella DTD.|  
  
 Anche se un attributo (*attr*) viene elencato come nodo nella sezione 1.2 Fundamental Interfaces della raccomandazione W3C DOM Level 1, non viene considerato come figlio di alcun nodo dell'elemento.  
  
 Nella tabella seguente vengono descritti i tipi di nodi aggiuntivi non definiti dalla W3C, ma disponibili per l'uso nel modello a oggetti Microsoft .NET Framework come enumerazioni **XmlNodeType**. Pertanto, per questi tipi di nodi non esiste una colonna del corrispondente Tipo di nodo DOM.  
  
|Tipo di nodo|Descrizione|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|Rappresenta il nodo della dichiarazione `<?xml version="1.0"…>`.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Rappresenta gli spazi vuoti significativi, ovvero gli spazi vuoti nel contenuto misto.|  
|<xref:System.Xml.XmlWhitespace>|Rappresenta gli spazi vuoti nel contenuto di un elemento.|  
|EndElement|Restituito quando **XmlReader** raggiunge la fine di un elemento.<br /><br /> Esempio di codice XML:**\</item>**<br /><br /> Per altre informazioni, vedere <xref:System.Xml.XmlNodeType>.|  
|EndEntity|Restituito quando **XmlReader** raggiunge la fine della sostituzione dell'entità come risultato di una chiamata a <xref:System.Xml.XmlReader.ResolveEntity%2A>. Per altre informazioni, vedere <xref:System.Xml.XmlNodeType>.|  
  
 Per visualizzare un esempio di codice che legge nell'XML e usa un costrutto di maiuscole e minuscole nei tipi di nodo per stampare informazioni sul nodo e sul relativo contenuto, vedere <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>.  
  
 Per altre informazioni sulla gerarchia di oggetti dei tipi di nodo e il nome di oggetto equivalente, vedere [Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)](xml-document-object-model-dom-hierarchy.md). Per altre informazioni sugli oggetti creati nell'albero dei nodi, vedere [Mapping della gerarchia di oggetti in dati XML](mapping-the-object-hierarchy-to-xml-data.md).  
  
## <a name="see-also"></a>Vedere anche

- [XML DOM (Document Object Model)](xml-document-object-model-dom.md)
