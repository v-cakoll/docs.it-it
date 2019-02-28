---
title: Costanti definite dall'utente (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: e519fcaf90c6f18e75d5c409cbe7067d5db36429
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975940"
---
# <a name="user-defined-constants-visual-basic"></a>Costanti definite dall'utente (Visual Basic)
Una costante è un nome significativo che prende il posto di un numero o una stringa che non cambia. Archiviano i valori che, come suggerisce il nome, rimangono costanti durante l'esecuzione di un'applicazione. È possibile usare le costanti che vengono definite tramite i controlli o si lavora con i componenti oppure è possibile crearne uno. Vengono descritte le costanti personalizzate come *definite dall'utente*.  
  
 Consente di dichiarare una costante con i `Const` istruzione, utilizzando le stesse linee guida si farebbe per la creazione di un nome di variabile. Se `Option Strict` è `On`, è necessario dichiarare in modo esplicito il tipo di costante.  
  
## <a name="const-statement-usage"></a>Utilizzo dell'istruzione const  
 Oggetto `Const` istruzione può rappresentare un matematiche o date/time quantity:  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 Inoltre possibile definire `String` costanti:  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 L'espressione a destra del segno di uguale ( `=` ) è spesso un numero o valore letterale stringa, ma può essere anche un'espressione che restituisce un numero o una stringa (anche se tale espressione non può contenere chiamate alle funzioni). È anche possibile definire le costanti in termini di costanti definite in precedenza:  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a>Ambito delle costanti definite dall'utente  
 Oggetto `Const` ambito dell'istruzione è uguale a quello di una variabile dichiarata nello stesso percorso. È possibile specificare l'ambito in uno dei modi seguenti:  
  
-   Per creare una costante che esiste solo all'interno di una routine, dichiararlo all'interno di tale procedura.  
  
-   Per creare una costante che sia disponibile per tutte le routine all'interno di una classe, ma non a qualsiasi codice all'esterno di tale modulo, dichiararlo nella sezione delle dichiarazioni della classe.  
  
-   Per creare una costante che sia disponibile per tutti i membri di un assembly, ma non ai client all'esterno dell'assembly, dichiarare usando il `Friend` parola chiave nella sezione delle dichiarazioni della classe.  
  
-   Per creare una costante disponibile in tutta l'applicazione, dichiarare usando il `Public` parola chiave nelle dichiarazioni di sezione la classe.  
  
 Per altre informazioni, vedere [Procedura: Dichiarare una costante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Evitare riferimenti circolari  
 Poiché le costanti possono essere definite in termini di altre costanti, è possibile creare inavvertitamente un *ciclo*, o riferimento circolare tra due o più costanti. Un ciclo si verifica quando si dispone di due o più costanti pubbliche, ognuno dei quali è definito in termini di altro, come nell'esempio seguente:  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 Se si verifica un ciclo, Visual Basic genera un errore del compilatore.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Costanti ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Cenni preliminari sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Procedura: Dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
