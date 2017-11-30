---
title: Copia di nodi esistenti
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 11f3915dfebd7ad9d3144c9bedcd7f42b4754359
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="copy-existing-nodes"></a>Copia di nodi esistenti
Sono disponibili numerosi metodi e proprietà nell'oggetto modello DOM (Document XML) consente di selezionare un nodo, ad esempio **SelectSingleNode**, **ChildNodes [int i]**, **attributi [int i]**. Una volta selezionato il nodo, è possibile inserirlo nell'albero mediante uno dei metodi di inserimento applicabili a quel determinato tipo di nodo. L'unica restrizione all'inserimento di un nodo nell'albero è che il documento deve conservare un formato corretto dopo l'inserimento del nodo. Quando un nodo esistente viene inserito nell'albero DOM, viene rimosso dalla posizione originale e aggiunto alla posizione di destinazione.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
