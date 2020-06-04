---
title: Risoluzione dei problemi relativi alle variabili
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
ms.openlocfilehash: 3efecf3883e5a1f49308af732a89ff66dc8b2421
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410322"
---
# <a name="troubleshooting-variables-in-visual-basic"></a>Risoluzione dei problemi relativi alle variabili in Visual Basic
In questa pagina vengono elencati alcuni problemi comuni che possono verificarsi quando si utilizzano le variabili in Visual Basic.  
  
## <a name="unable-to-access-members-of-an-object"></a>Impossibile accedere ai membri di un oggetto  
 Se il codice tenta di accedere a una proprietà o metodo su un oggetto, possono verificarsi due diversi errori:  
  
- Il compilatore può generare un messaggio di errore se si dichiara la variabile oggetto con un tipo specifico e poi si fa riferimento a un membro che non è definito con quel tipo.  
  
- Un <xref:System.MemberAccessException> della fase di esecuzione si verifica quando l'oggetto assegnato a una variabile oggetto non espone il membro a cui il codice tenta di accedere. Nel caso di una variabile di [Object Data Type](../../../language-reference/data-types/object-data-type.md), è anche possibile ottenere questa eccezione se il membro non è `Public`. Questo perché l'associazione tardiva consente l'accesso solo ai membri `Public` .  
  
 Quando il [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) imposta `On`per il controllo del tipo, una variabile oggetto può accedere solo ai metodi e alle proprietà della classe con cui viene dichiarata. Questa condizione è illustrata nell'esempio seguente.  

 [!code-vb[VbVbalrVariables#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#2)]  
  
 In questo esempio `p` può usare solo i membri della classe <xref:System.Object> stessa, che non includono la proprietà `Left` . D'altra parte, `q` è stata dichiarata con il tipo <xref:System.Windows.Forms.Label>, perciò può usare tutti i metodi e le proprietà della classe <xref:System.Windows.Forms.Label> nello spazio dei nomi <xref:System.Windows.Forms> .  
  
### <a name="correct-approach"></a>Approccio corretto  
 Per poter accedere a tutti i membri di un oggetto di una determinata classe, dichiarare la variabile oggetto con il tipo di tale classe dove possibile. Se questo è non possibile, ad esempio quando non si conosce il tipo di oggetto in fase di compilazione, è necessario impostare `Option Strict` su `Off` e dichiarare la variabile come [Object Data Type](../../../language-reference/data-types/object-data-type.md). In questo modo oggetti di qualsiasi tipo possono essere assegnati alla variabile, perciò occorre eseguire i passaggi necessari per assicurarsi che l'oggetto attualmente assegnato sia di un tipo accettabile. Per eseguire questa determinazione, è possibile usare l' [operatore typeof](../../../language-reference/operators/typeof-operator.md) .  
  
## <a name="other-components-cannot-access-your-variable"></a>Altri componenti non possono accedere alla variabile  
 I nomi di Visual Basic non fanno *distinzione tra maiuscole e*minuscole. Se due nomi differiscono solo nelle maiuscole, il compilatore li interpreta come un unico nome. Ad esempio, se si ha `ABC` e `abc` , il compilatore li interpreta come se facessero riferimento allo stesso elemento dichiarato.  
  
 Il Common Language Runtime (CLR) usa invece l'associazione *che distingue fra maiuscole e minuscole* . Perciò, quando si genera un assembly o una DLL e la si rende disponibile ad altri assembly, i nomi distinguono fra maiuscole e minuscole. Se ad esempio si definisce una classe con un elemento denominato `ABC`e altri assembly usano la classe mediante il Common Language Runtime, devono fare riferimento all'elemento come `ABC`. Se in seguito si ricompila la classe e si cambia il nome dell'elemento in `abc`, gli altri assembly che usano la classe non possono più accedere a quell'elemento. Pertanto, quando si rilascia una versione aggiornata di un assembly, non si devono modificare le maiuscole e le minuscole degli elementi pubblici.  
  
 Per altre informazioni, vedere [Common Language Runtime](../../../../standard/clr.md).  
  
### <a name="correct-approach"></a>Approccio corretto  
 Per consentire agli altri componenti di accedere alle variabili, trattare i loro nomi come se distinguessero fra maiuscole e minuscole. Quando si testa la classe o il modulo, assicurarsi che gli altri assembly si associno alle variabili giuste. Dopo aver pubblicato un componente, non apportare modifiche ai nomi delle variabili esistenti e neppure alla loro combinazione di maiuscole e minuscole.  
  
## <a name="wrong-variable-being-used"></a>Variabile usata non corretta  
 Quando si dispone di più di una variabile con lo stesso nome, il Visual Basic compilatore tenta di risolvere ogni riferimento a tale nome. Se le variabili hanno un ambito diverso, il compilatore risolve il riferimento secondo la dichiarazione con l'ambito più ristretto. Se hanno lo stesso ambito, la risoluzione non riuscirà e il compilatore segnalerà un errore. Per altre informazioni, vedere [References to Declared Elements](../declared-elements/references-to-declared-elements.md).  
  
### <a name="correct-approach"></a>Approccio corretto  
 Evitare l'uso di variabili con lo stesso nome ma un ambito diverso. Se si usano altri assembly o progetti, evitare il più possibile l'uso di nomi definiti in questi componenti esterni. Se si hanno più variabili con lo stesso nome, assicurarsi di qualificare ogni riferimento a esso. Per altre informazioni, vedere [References to Declared Elements](../declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Vedere anche

- [Variabili](index.md)
- [Dichiarazione di variabile](variable-declaration.md)
- [Variabili oggetto](object-variables.md)
- [Dichiarazione di variabili oggetto](object-variable-declaration.md)
- [Procedura: accedere ai membri di un oggetto](how-to-access-members-of-an-object.md)
- [Valori di variabili oggetto](object-variable-values.md)
- [Procedura: determinare a quale tipo fa riferimento una variabile oggetto](how-to-determine-what-type-an-object-variable-refers-to.md)
- [References to Declared Elements](../declared-elements/references-to-declared-elements.md)
- [Declared Element Names](../declared-elements/declared-element-names.md)
