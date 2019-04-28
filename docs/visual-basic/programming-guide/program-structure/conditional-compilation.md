---
title: Compilazione condizionale in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 828edf2e5491394f5ac802b5c9babfb3df359e59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758457"
---
# <a name="conditional-compilation-in-visual-basic"></a>Compilazione condizionale in Visual Basic
Nelle *compilazione condizionale*, determinati blocchi di codice in un programma vengono compilati in modo selettivo, mentre altre vengono ignorate.  
  
 Ad esempio, è possibile scrivere il debug di istruzioni che confrontano la velocità dei diversi approcci per l'attività di programmazione stesso, oppure è possibile localizzare un'applicazione per più lingue. Le istruzioni di compilazione condizionale sono progettate per l'esecuzione durante la fase di compilazione, non in fase di esecuzione.  
  
 È possibile indicare i blocchi di codice da compilare in modo condizionale con il `#If...Then...#Else` direttiva. Ad esempio, per creare il francese e tedesco versioni della stessa applicazione dallo stesso codice sorgente, si incorporano i segmenti di codice specifico della piattaforma nel `#If...Then` istruzioni che utilizzano costanti predefinite `FrenchVersion` e `GermanVersion`. Nell'esempio seguente viene illustrato come:  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 Se si imposta il valore della `FrenchVersion` costante di compilazione condizionale a `True` in fase di compilazione, il codice condizionale per la versione francese viene compilato. Se si imposta il valore della `GermanVersion` costante a `True`, il compilatore Usa la versione tedesca. Se nessuna delle due è impostata su `True`, il codice nell'ultimo `Else` bloccare l'esecuzione.  
  
> [!NOTE]
>  Completamento automatico verrà non funziona quando la modifica del codice e l'uso di direttive di compilazione condizionale se il codice non fa parte di current branch.  
  
## <a name="declaring-conditional-compilation-constants"></a>La dichiarazione di costanti di compilazione condizionale  
 È possibile impostare le costanti di compilazione condizionale in uno dei tre modi:  
  
- Nel **Progettazione progetti**  
  
- Nella riga di comando quando si usa il compilatore della riga di comando  
  
- Nel codice  
  
 Costanti di compilazione condizionale hanno un ambito speciale e non è possibile accedervi dal codice standard. L'ambito di una costante di compilazione condizionale dipende dal modo in cui è impostata. La tabella seguente elenca l'ambito delle costanti dichiarato tramite ognuno dei tre metodi indicati in precedenza.  
  
|Modalità di impostazione (costante)|Ambito della costante|  
|---|---|  
|**Creazione progetti**|Public per tutti i file di progetto|  
|Riga di comando|Public per tutti i file passati al compilatore della riga di comando|  
|`#Const` istruzione nel codice|Private del file in cui è dichiarata|  
  
|Per impostare le costanti in Creazione progetti|  
|---|  
|-Prima di creare il file eseguibile, impostare le costanti **creazione progetti** seguendo i passaggi forniti nella [gestione dei progetti e le proprietà della soluzione](/visualstudio/ide/managing-project-and-solution-properties).|  
  
|Per impostare le costanti nella riga di comando|  
|---|  
|-Usare il **/d** switch per inserire le costanti di compilazione condizionale, come nell'esempio seguente:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     Spazio non è necessario tra i **/d** switch e la prima costante. Per altre informazioni, vedere [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Le dichiarazioni della riga di comando esegue l'override di dichiarazioni immesso nel **Progettazione progetti**, ma non cancellarne il contenuto. Impostare gli argomenti **Progettazione progetti** rimangono valide per le compilazioni successive.<br />     Quando si scrivono le costanti nel codice stesso, non sono presenti regole strict per quanto riguarda la loro posizione, perché il relativo ambito sia l'intero modulo in cui sono dichiarate.|  
  
|Per impostare le costanti nel codice|  
|---|  
|-Collocare le costanti nel blocco di dichiarazione del modulo in cui vengono usati. Ciò consente di mantenere il codice organizzato e facili da leggere.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|---|---|  
|[Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Vengono forniti suggerimenti per rendere il codice facile da leggere e gestire.|  
  
## <a name="reference"></a>Riferimenti  
 [Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
