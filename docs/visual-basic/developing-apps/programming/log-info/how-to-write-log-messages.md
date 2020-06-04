---
title: 'Procedura: Scrivere messaggi di log'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 28c5fe77e2711dfcac96e621a90fb9506eb74775
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410049"
---
# <a name="how-to-write-log-messages-visual-basic"></a>Procedura: scrivere messaggi di log (Visual Basic)

È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare le informazioni sull'applicazione. Questo esempio illustra come usare il metodo `My.Application.Log.WriteEntry` per registrare le informazioni di traccia.

Per registrare le informazioni sulle eccezioni, usare il metodo `My.Application.Log.WriteException`. Vedere [Procedura: Registrare eccezioni](how-to-log-exceptions.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene usato il metodo `My.Application.Log.WriteEntry` per scrivere le informazioni di traccia.

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a>Sicurezza di .NET Framework

Verificare che i dati scritti nel log non contengano informazioni riservate, ad esempio le password degli utenti. Per altre informazioni, vedere [Uso dei log applicazione](working-with-application-logs.md).

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Utilizzo dei log applicazione](working-with-application-logs.md)
- [Procedura: Registrare eccezioni](how-to-log-exceptions.md)
- [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](walkthrough-determining-where-my-application-log-writes-information.md)
- [Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log](walkthrough-changing-where-my-application-log-writes-information.md)
- [Procedura dettagliata: Filtro dell'output di My.Application.Log](walkthrough-filtering-my-application-log-output.md)
