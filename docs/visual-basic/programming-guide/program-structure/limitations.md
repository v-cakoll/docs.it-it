---
title: Limitazioni
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 46294b68bda8a5d2d21c0e4efea6a78e6a265ffe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403187"
---
# <a name="visual-basic-limitations"></a>Limitazioni di Visual Basic
Le versioni precedenti di Visual Basic applicano limiti nel codice, ad esempio la lunghezza dei nomi delle variabili, il numero di variabili consentite nei moduli e le dimensioni del modulo. In Visual Basic .NET queste restrizioni sono state attenuate, garantendo una maggiore libertà di scrittura e disposizione del codice.  
  
 I limiti fisici dipendono maggiormente dalla memoria in fase di esecuzione rispetto alle considerazioni in fase di compilazione. Se si usano procedure di programmazione prudenti e si dividono applicazioni di grandi dimensioni in più classi e moduli, è possibile che si verifichi una limitazione di Visual Basic interna.  
  
 Di seguito sono riportate alcune limitazioni che è possibile riscontrare in casi estremi:  
  
- **Lunghezza del nome.** È presente un numero massimo di caratteri per il nome di ogni elemento di programmazione dichiarato. Questo valore massimo si applica a un'intera stringa di qualificazione se il nome dell'elemento è qualificato. Vedere [Declared Element Names](../language-features/declared-elements/declared-element-names.md).  
  
- **Lunghezza riga.** È presente un massimo di 65535 caratteri in una riga fisica di codice sorgente. La riga di codice sorgente logica può essere più lunga se si utilizzano caratteri di continuazione di riga. Vedere [procedura: interrompere e combinare istruzioni nel codice](how-to-break-and-combine-statements-in-code.md).  
  
- **Dimensioni della matrice.** Per una matrice è possibile dichiarare un numero massimo di dimensioni. Questo limita il numero di indici che è possibile utilizzare per specificare un elemento di matrice. Vedere [dimensioni della matrice in Visual Basic](../language-features/arrays/array-dimensions.md).  
  
- **Lunghezza della stringa.** È disponibile un numero massimo di caratteri Unicode che è possibile archiviare in una singola stringa. Vedere [tipo di dati String](../../language-reference/data-types/string-data-type.md).  
  
- **Lunghezza della stringa dell'ambiente.** Per qualsiasi stringa di ambiente utilizzata come argomento della riga di comando è disponibile un massimo di 32768 caratteri. Si tratta di una limitazione per tutte le piattaforme.  
  
## <a name="see-also"></a>Vedere anche

- [Struttura del programma e convenzioni del codice](program-structure-and-code-conventions.md)
- [Convenzioni di denominazione di Visual Basic](naming-conventions.md)
