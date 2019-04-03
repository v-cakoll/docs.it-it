---
title: 'Procedura: Dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: fb6411efc190dce335422369a8d2bbff564b9523
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819671"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Procedura: Dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic
Si dichiara una variabile del [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) specificando `As Object` in un [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Si assegna un oggetto a tale variabile posizionando l'oggetto dopo il segno di uguale (`=`) in una clausola di istruzione o l'inizializzazione di assegnazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato un `Object` variabile e assegna a esso dell'istanza corrente.  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 È possibile combinare la dichiarazione e l'assegnazione inizializzando la variabile come parte della relativa dichiarazione. Nell'esempio seguente è equivalente all'esempio precedente.  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un riferimento allo spazio dei nomi <xref:System>.  
  
-   Una classe, struttura o modulo in cui inserire il `Dim` istruzione.  
  
-   Una procedura in cui inserire l'istruzione di assegnazione.  
  
## <a name="see-also"></a>Vedere anche

- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
