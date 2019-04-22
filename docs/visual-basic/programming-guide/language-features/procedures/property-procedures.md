---
title: Routine Property (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: 47e93ee17f160ce5cd701fd0a12ec16b3997ce9b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828349"
---
# <a name="property-procedures-visual-basic"></a>Routine Property (Visual Basic)
Una routine di proprietà è una serie di istruzioni di Visual Basic che consentono di modificare una proprietà personalizzata in un modulo, classe o struttura. Le routine della proprietà sono dette anche *funzioni di accesso proprietà*.  
  
 Visual Basic fornisce le routine della proprietà seguente:  
  
-   Oggetto `Get` procedure restituisce il valore di una proprietà. Viene chiamato quando si accede alla proprietà in un'espressione.  
  
-   Oggetto `Set` routine imposta una proprietà su un valore, incluso un riferimento all'oggetto. Viene chiamato quando si assegna un valore alla proprietà.  
  
 Le routine della proprietà in genere definite in coppie, mediante il `Get` e `Set` istruzioni, ma è possibile definire entrambe le procedure da solo se la proprietà è di sola lettura ([l'istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o in sola lettura ([impostata Istruzione](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 È possibile omettere il `Get` e `Set` procedura quando si usa una proprietà implementata automaticamente. Per altre informazioni, vedere [Proprietà implementate automaticamente](./auto-implemented-properties.md).  
  
 È possibile definire le proprietà nelle classi, strutture e i moduli. Le proprietà sono `Public` per impostazione predefinita, il che significa che è possibile chiamarle da qualsiasi posizione nell'applicazione che possa accedere al contenitore della proprietà.  
  
 Per un confronto tra proprietà e variabili, vedere [differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 Una proprietà è definita da un blocco di codice incluso all'interno di [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) e il `End Property` istruzione. All'interno del blocco, ogni routine della proprietà viene visualizzata come un blocco interno racchiuso in un'istruzione di dichiarazione (`Get` oppure `Set`) e il corrispondente `End` dichiarazione.  
  
 La sintassi per dichiarare una proprietà e le relative procedure è come segue:  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 Il `Modifiers` può specificare il livello di accesso e le informazioni riguardanti l'overload, si esegue l'override, la condivisione e shadowing, nonché se la proprietà è di sola lettura o in sola lettura. Il `AccessLevel` nella `Get` o `Set` routine può essere di qualsiasi livello più restrittivo rispetto al livello di accesso specificato per la proprietà stessa. Per altre informazioni, vedere [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Tipo di dati  
 Tipo di dati della proprietà e il livello di accesso dell'entità sono definiti nel `Property` istruzione, non nella routine della proprietà. Una proprietà può avere solo un tipo di dati. Ad esempio, è possibile definire una proprietà per archiviare una `Decimal` valore ma che recuperano un `Double` valore.  
  
### <a name="access-level"></a>Livello di accesso  
 Tuttavia, è possibile definire un livello di accesso dell'entità per una proprietà e limitare ulteriormente il livello di accesso in una delle routine della proprietà. Ad esempio, è possibile definire un `Public` proprietà, quindi definire un `Private Set` procedure. Il `Get` rimane impostato su procedure `Public`. È possibile modificare il livello di accesso in solo una delle routine della proprietà e si può solo rendono più restrittivo del livello di accesso dell'entità. Per altre informazioni, vedere [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Dichiarazione di parametro  
 Ogni parametro è dichiarare la stessa procedura valida per [routine Sub](./sub-procedures.md), ad eccezione del fatto che il meccanismo di passaggio deve essere `ByVal`.  
  
 La sintassi per ogni parametro nell'elenco dei parametri è come segue:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione. La sintassi per specificare un valore predefinito è come segue:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Valore proprietà  
 In un `Get` procedure, il valore restituito viene fornita all'espressione chiamante come valore della proprietà.  
  
 In un `Set` routine, il nuovo valore della proprietà viene passato al parametro il `Set` istruzione. Se si dichiara in modo esplicito un parametro, è necessario dichiararla con lo stesso tipo di dati della proprietà. Se non si dichiara un parametro, il compilatore Usa il parametro implicito `Value` per rappresentare il nuovo valore da assegnare alla proprietà.  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Una routine di proprietà è richiamare in modo implicito facendo riferimento alla proprietà. Si utilizza il nome della proprietà simile a quello è necessario usare il nome di una variabile, ad eccezione del fatto che è necessario fornire valori per tutti gli argomenti che non sono facoltativi ed è necessario racchiudere l'elenco di argomenti racchiuso tra parentesi. Se viene fornito alcun argomento, è possibile omettere le parentesi.  
  
 La sintassi per una chiamata implicita a un `Set` procedura è la seguente:  
  
 `propertyname[(argumentlist)] = expression`  
  
 La sintassi per una chiamata implicita a un `Get` procedura è la seguente:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione di dichiarazione e di chiamata  
 La proprietà seguente archivia un nome completo come due parti costitutive, il nome e cognome. Quando legge il codice chiamante `fullName`, il `Get` procedure combina le due parti costitutive e restituisce il nome completo. Quando il codice chiamante assegna un nuovo nome completo, il `Set` routine tenta di suddividere l'operazione in due parti costitutive. Se non viene trovato uno spazio, li archivia tutti come il nome.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 L'esempio seguente illustra tipici chiamate alle routine della proprietà di `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Function](./function-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Chiamare una routine Property](./how-to-call-a-property-procedure.md)
- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
