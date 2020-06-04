---
title: Costanti definite dall'utente
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 14f3de39eb8d8e6820e2b40792a8e8e57217e410
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414376"
---
# <a name="user-defined-constants-visual-basic"></a>Costanti definite dall'utente (Visual Basic)
Una costante è un nome significativo che prende il posto di un numero o di una stringa che non cambia. Archiviano i valori che, come suggerisce il nome, rimangono costanti durante l'esecuzione di un'applicazione. È possibile usare le costanti definite dai controlli o dai componenti usati oppure è possibile crearne di personalizzati. Le costanti create dall'utente vengono descritte come *definite dall'utente*.  
  
 Viene dichiarata una costante con l' `Const` istruzione, usando le stesse linee guida per la creazione di un nome di variabile. Se `Option Strict` è `On` , è necessario dichiarare in modo esplicito il tipo di costante.  
  
## <a name="const-statement-usage"></a>Utilizzo istruzioni Const  
 Un' `Const` istruzione può rappresentare una quantità matematica o di data/ora:  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 Consente inoltre di definire `String` costanti:  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 L'espressione a destra del segno di uguale ( `=` ) è spesso un numero o una stringa letterale, ma può anche essere un'espressione che restituisce un numero o una stringa (anche se tale espressione non può contenere chiamate alle funzioni). È anche possibile definire costanti in termini di costanti definite in precedenza:  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a>Ambito delle costanti definite dall'utente  
 `Const`L'ambito di un'istruzione è identico a quello di una variabile dichiarata nella stessa posizione. È possibile specificare l'ambito in uno dei modi seguenti:  
  
- Per creare una costante che esiste solo all'interno di una routine, dichiararla all'interno di tale procedura.  
  
- Per creare una costante disponibile per tutte le routine all'interno di una classe, ma non per il codice esterno a tale modulo, dichiararla nella sezione delle dichiarazioni della classe.  
  
- Per creare una costante disponibile a tutti i membri di un assembly, ma non all'esterno dei client dell'assembly, dichiararla usando la `Friend` parola chiave nella sezione delle dichiarazioni della classe.  
  
- Per creare una costante disponibile nell'applicazione, dichiararla usando la `Public` parola chiave nella sezione delle dichiarazioni della classe.  
  
 Per altre informazioni, vedere [procedura: dichiarare una costante](how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Evitare riferimenti circolari  
 Poiché le costanti possono essere definite in termini di altre costanti, è possibile creare inavvertitamente un *ciclo*o un riferimento circolare tra due o più costanti. Si verifica un ciclo quando si hanno due o più costanti pubbliche, ciascuna delle quali è definita in base all'altra, come nell'esempio seguente:  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 Se si verifica un ciclo, Visual Basic genera un errore del compilatore.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Const](../../../language-reference/statements/const-statement.md)
- [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)
- [Costanti ed enumerazioni](index.md)
- [Costanti ed enumerazioni](../../../language-reference/constants-and-enumerations.md)
- [Cenni preliminari sulle enumerazioni](enumerations-overview.md)
- [Cenni preliminari sulle costanti](constants-overview.md)
- [Procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md)
- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)
