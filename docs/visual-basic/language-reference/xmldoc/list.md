---
title: <list>
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 955c1a4c5c5619f908b8d03dbf12360c23574478
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400086"
---
# <a name="list-visual-basic"></a>\<list> (Visual Basic)
Definisce un elenco o una tabella.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
## <a name="parameters"></a>Parametri  
 `type`  
 Tipo dell'elenco. Deve essere un "Bullet" per un elenco puntato, "Number" per un elenco numerato o "Table" per una tabella a due colonne.  
  
 `term`  
 Utilizzato solo quando `type` è "Table". Termine da definire, definito nel tag Description.  
  
 `description`  
 Quando `type` è "Bullet" o "Number", `description` è un elemento nell'elenco quando `type` è "Table", `description` è la definizione di `term` .  
  
## <a name="remarks"></a>Commenti  
 Il `<listheader>` blocco definisce l'intestazione di un elenco di tabelle o definizioni. Quando si definisce una tabella, è sufficiente specificare una voce per `term` nell'intestazione.  
  
 Ogni elemento nell'elenco viene specificato con un `<item>` blocco. Quando si crea un elenco di definizioni, è necessario specificare sia che `term` `description` . Tuttavia, per una tabella, un elenco puntato o un elenco numerato, è sufficiente fornire una voce per `description` .  
  
 Un elenco o una tabella può includere un numero di `<item>` blocchi sufficiente.  
  
 Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il `<list>` tag per definire un elenco puntato nella sezione Osservazioni.  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](index.md)
