---
title: Copia di nodi esistenti
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: fb9ccd7b16d00355ba87bb32f5447906feeecd94
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711064"
---
# <a name="copy-existing-nodes"></a>Copia di nodi esistenti
Nel DOM (Document Object Model) XML sono disponibili molti metodi e proprietà che è possibile usare per selezionare un nodo, ad esempio **SelectSingleNode**, **ChildNodes[int i]** e **Attributes[int i]** . Una volta selezionato il nodo, è possibile inserirlo nell'albero mediante uno dei metodi di inserimento applicabili a quel determinato tipo di nodo. L'unica restrizione all'inserimento di un nodo nell'albero è che il documento deve conservare un formato corretto dopo l'inserimento del nodo. Quando un nodo esistente viene inserito nell'albero DOM, viene rimosso dalla posizione originale e aggiunto alla posizione di destinazione.  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
