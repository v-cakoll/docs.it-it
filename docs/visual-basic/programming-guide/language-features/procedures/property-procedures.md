---
title: Routine Property (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbdf49d5c3eb5ef71b25a060d62f55f19098f445
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="property-procedures-visual-basic"></a>Routine Property (Visual Basic)
Una routine della proprietà è una serie di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] istruzioni che modificano una proprietà personalizzata di un modulo, classe o struttura. Le routine della proprietà sono anche noti come *accesso della proprietà*.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]fornisce le routine della proprietà seguente:  
  
-   Oggetto `Get` procedura restituisce il valore di una proprietà. Viene chiamato quando si accede alla proprietà in un'espressione.  
  
-   Oggetto `Set` routine imposta una proprietà su un valore, incluso un riferimento all'oggetto. Viene chiamato quando si assegna un valore alla proprietà.  
  
 È in genere definire le routine di proprietà in coppie, mediante il `Get` e `Set` istruzione, ma è possibile definire una routine singolarmente se la proprietà è di sola lettura ([l'istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o di sola scrittura ([impostato Istruzione](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 È possibile omettere il `Get` e `Set` procedura quando si usa una proprietà implementata automaticamente. Per altre informazioni, vedere [Proprietà implementate automaticamente](./auto-implemented-properties.md).  
  
 È possibile definire le proprietà nelle classi, strutture e i moduli. Le proprietà sono `Public` per impostazione predefinita, il che significa che è possibile chiamarle da qualsiasi punto dell'applicazione che è possibile accedere al contenitore della proprietà.  
  
 Per un confronto tra proprietà e variabili, vedere [le differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 Una proprietà è definita da un blocco di codice incluso all'interno di [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md) e `End Property` istruzione. All'interno del blocco, ogni routine della proprietà viene visualizzato come un blocco interno racchiuso tra un'istruzione di dichiarazione (`Get` o `Set`) e il corrispondente `End` dichiarazione.  
  
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
  
 Il `Modifiers` può specificare il livello di accesso e le informazioni su overload, override, condivisione e shadowing, nonché se la proprietà è di sola lettura o in sola lettura. Il `AccessLevel` sul `Get` o `Set` procedura può essere qualsiasi livello più restrittivo rispetto al livello di accesso specificato per la proprietà stessa. Per ulteriori informazioni, vedere [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Tipo di dati  
 Tipo di dati di una proprietà e il livello di accesso dell'entità sono definiti nel `Property` istruzione, non nelle routine della proprietà. Una proprietà può avere solo un tipo di dati. Ad esempio, è possibile definire una proprietà per archiviare un `Decimal` valore ma che recuperano un `Double` valore.  
  
### <a name="access-level"></a>Livello di accesso  
 Tuttavia, è possibile definire un livello di accesso dell'entità per una proprietà e limitare ulteriormente il livello di accesso in una delle routine della proprietà. Ad esempio, è possibile definire un `Public` proprietà e quindi definire un `Private Set` stored procedure. Il `Get` procedura rimane `Public`. È possibile modificare il livello di accesso in sola delle routine della proprietà e, è possibile solo apportare più restrittivo rispetto al livello di accesso dell'entità. Per ulteriori informazioni, vedere [procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Dichiarazione di parametro  
 Ciascun parametro viene dichiarato esattamente come avviene per [Sub (routine)](./sub-procedures.md), ad eccezione del fatto che il meccanismo di passaggio deve essere `ByVal`.  
  
 La sintassi per ogni parametro nell'elenco di parametri è come segue:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione. La sintassi per specificare un valore predefinito è come segue:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Valore proprietà  
 In un `Get` procedure, il valore restituito viene fornita all'espressione chiamante come valore della proprietà.  
  
 In un `Set` procedure, il nuovo valore della proprietà viene passato al parametro del `Set` istruzione. Se si dichiara in modo esplicito un parametro, è necessario dichiararla con lo stesso tipo di dati della proprietà. Se non si dichiara un parametro, il compilatore utilizza il parametro implicito `Value` per rappresentare il nuovo valore da assegnare alla proprietà.  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Richiamare una routine di proprietà in modo implicito facendo riferimento alla proprietà. Utilizzare il nome della proprietà esattamente come si utilizzerebbe il nome di una variabile, ad eccezione del fatto che è necessario fornire valori per tutti gli argomenti non facoltativi e, è necessario racchiudere l'elenco di argomenti tra parentesi. Se non vengono forniti argomenti, è possibile omettere le parentesi.  
  
 La sintassi per una chiamata implicita a un `Set` procedura è la seguente:  
  
 `propertyname[(argumentlist)] = expression`  
  
 La sintassi per una chiamata implicita a un `Get` procedura è la seguente:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione di dichiarazione e chiamata  
 La seguente proprietà archiviato un nome completo come due parti costitutive, il nome e il cognome. Quando viene letto il codice chiamante `fullName`, `Get` procedure combina le due parti costitutive e restituisce il nome completo. Quando il codice chiamante viene assegnato un nuovo nome completo, il `Set` routine tenta di suddividerla in due parti costitutive. Se non viene trovato uno spazio, memorizzato tutto come il nome.  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 L'esempio seguente mostra le chiamate alle routine della proprietà di tipiche `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Function](./function-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)  
 [Procedura: Creare una proprietà](./how-to-create-a-property.md)  
 [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)  
 [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)  
 [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
