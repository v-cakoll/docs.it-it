---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43750009"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="9d7fb-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="9d7fb-102">ODBC Schema Collections</span></span>
<span data-ttu-id="9d7fb-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="9d7fb-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="9d7fb-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d7fb-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="9d7fb-105">Il Driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="9d7fb-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d7fb-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7fb-106">Tables</span></span>  
  
-   <span data-ttu-id="9d7fb-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7fb-107">Indexes</span></span>  
  
-   <span data-ttu-id="9d7fb-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7fb-108">Columns</span></span>  
  
-   <span data-ttu-id="9d7fb-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-109">Procedures</span></span>  
  
-   <span data-ttu-id="9d7fb-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d7fb-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9d7fb-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d7fb-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9d7fb-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d7fb-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="9d7fb-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="9d7fb-113">Tables and Views</span></span>  
  
|<span data-ttu-id="9d7fb-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-114">ColumnName</span></span>|<span data-ttu-id="9d7fb-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9d7fb-116">TABLE_CAT</span></span>|<span data-ttu-id="9d7fb-117">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-117">String</span></span>|  
|<span data-ttu-id="9d7fb-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9d7fb-118">TABLE_SCHEM</span></span>|<span data-ttu-id="9d7fb-119">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-119">String</span></span>|  
|<span data-ttu-id="9d7fb-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-120">TABLE_NAME</span></span>|<span data-ttu-id="9d7fb-121">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-121">String</span></span>|  
|<span data-ttu-id="9d7fb-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-122">TABLE_TYPE</span></span>|<span data-ttu-id="9d7fb-123">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-123">String</span></span>|  
|<span data-ttu-id="9d7fb-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-124">REMARKS</span></span>|<span data-ttu-id="9d7fb-125">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9d7fb-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7fb-126">Indexes</span></span>  
  
|<span data-ttu-id="9d7fb-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-127">ColumnName</span></span>|<span data-ttu-id="9d7fb-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9d7fb-129">TABLE_CAT</span></span>|<span data-ttu-id="9d7fb-130">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-130">String</span></span>|  
|<span data-ttu-id="9d7fb-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9d7fb-131">TABLE_SCHEM</span></span>|<span data-ttu-id="9d7fb-132">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-132">String</span></span>|  
|<span data-ttu-id="9d7fb-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-133">TABLE_NAME</span></span>|<span data-ttu-id="9d7fb-134">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-134">String</span></span>|  
|<span data-ttu-id="9d7fb-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-135">NON_UNIQUE</span></span>|<span data-ttu-id="9d7fb-136">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-136">Int16</span></span>|  
|<span data-ttu-id="9d7fb-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-138">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-138">String</span></span>|  
|<span data-ttu-id="9d7fb-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-139">INDEX_NAME</span></span>|<span data-ttu-id="9d7fb-140">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-140">String</span></span>|  
|<span data-ttu-id="9d7fb-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-141">TYPE</span></span>|<span data-ttu-id="9d7fb-142">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-142">Int16</span></span>|  
|<span data-ttu-id="9d7fb-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-144">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-144">Int16</span></span>|  
|<span data-ttu-id="9d7fb-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-145">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-146">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-146">String</span></span>|  
|<span data-ttu-id="9d7fb-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="9d7fb-147">ASC_OR_DESC</span></span>|<span data-ttu-id="9d7fb-148">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-148">String</span></span>|  
|<span data-ttu-id="9d7fb-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="9d7fb-149">CARDINATLITY</span></span>|<span data-ttu-id="9d7fb-150">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-150">Int32</span></span>|  
|<span data-ttu-id="9d7fb-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="9d7fb-151">PAGES</span></span>|<span data-ttu-id="9d7fb-152">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-152">Int32</span></span>|  
|<span data-ttu-id="9d7fb-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-153">FILTER_CONDITION</span></span>|<span data-ttu-id="9d7fb-154">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-154">String</span></span>|  
|<span data-ttu-id="9d7fb-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7fb-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9d7fb-156">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-156">String</span></span>|  
|<span data-ttu-id="9d7fb-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-158">Byte</span><span class="sxs-lookup"><span data-stu-id="9d7fb-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d7fb-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7fb-159">Columns</span></span>  
  
|<span data-ttu-id="9d7fb-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-160">ColumnName</span></span>|<span data-ttu-id="9d7fb-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="9d7fb-162">TABLE_CAT</span></span>|<span data-ttu-id="9d7fb-163">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-163">String</span></span>|  
|<span data-ttu-id="9d7fb-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9d7fb-164">TABLE_SCHEM</span></span>|<span data-ttu-id="9d7fb-165">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-165">String</span></span>|  
|<span data-ttu-id="9d7fb-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-166">TABLE_NAME</span></span>|<span data-ttu-id="9d7fb-167">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-167">String</span></span>|  
|<span data-ttu-id="9d7fb-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-168">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-169">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-169">String</span></span>|  
|<span data-ttu-id="9d7fb-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-170">DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-171">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-171">Int16</span></span>|  
|<span data-ttu-id="9d7fb-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-172">TYPE_NAME</span></span>|<span data-ttu-id="9d7fb-173">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-173">String</span></span>|  
|<span data-ttu-id="9d7fb-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-174">COLUMN_SIZE</span></span>|<span data-ttu-id="9d7fb-175">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-175">Int32</span></span>|  
|<span data-ttu-id="9d7fb-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="9d7fb-177">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-177">Int32</span></span>|  
|<span data-ttu-id="9d7fb-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9d7fb-179">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-179">Int16</span></span>|  
|<span data-ttu-id="9d7fb-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9d7fb-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9d7fb-181">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-181">Int16</span></span>|  
|<span data-ttu-id="9d7fb-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-182">NULLABLE</span></span>|<span data-ttu-id="9d7fb-183">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-183">Int16</span></span>|  
|<span data-ttu-id="9d7fb-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-184">REMARKS</span></span>|<span data-ttu-id="9d7fb-185">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-185">String</span></span>|  
|<span data-ttu-id="9d7fb-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9d7fb-186">COLUMN_DEF</span></span>|<span data-ttu-id="9d7fb-187">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-187">String</span></span>|  
|<span data-ttu-id="9d7fb-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-189">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-189">Int16</span></span>|  
|<span data-ttu-id="9d7fb-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9d7fb-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9d7fb-191">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-191">Int16</span></span>|  
|<span data-ttu-id="9d7fb-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7fb-193">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-193">Int32</span></span>|  
|<span data-ttu-id="9d7fb-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-195">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-195">Int32</span></span>|  
|<span data-ttu-id="9d7fb-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-196">IS_NULLABLE</span></span>|<span data-ttu-id="9d7fb-197">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-197">String</span></span>|  
|<span data-ttu-id="9d7fb-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7fb-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9d7fb-199">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-199">String</span></span>|  
|<span data-ttu-id="9d7fb-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7fb-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9d7fb-201">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-201">String</span></span>|  
|<span data-ttu-id="9d7fb-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-203">Byte</span><span class="sxs-lookup"><span data-stu-id="9d7fb-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d7fb-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-204">Procedures</span></span>  
  
|<span data-ttu-id="9d7fb-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-205">ColumnName</span></span>|<span data-ttu-id="9d7fb-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9d7fb-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="9d7fb-208">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-208">String</span></span>|  
|<span data-ttu-id="9d7fb-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9d7fb-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9d7fb-210">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-210">String</span></span>|  
|<span data-ttu-id="9d7fb-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7fb-212">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-212">String</span></span>|  
|<span data-ttu-id="9d7fb-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9d7fb-214">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-214">Int32</span></span>|  
|<span data-ttu-id="9d7fb-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9d7fb-216">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-216">Int32</span></span>|  
|<span data-ttu-id="9d7fb-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9d7fb-218">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-218">Int32</span></span>|  
|<span data-ttu-id="9d7fb-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-219">REMARKS</span></span>|<span data-ttu-id="9d7fb-220">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-220">String</span></span>|  
|<span data-ttu-id="9d7fb-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d7fb-222">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9d7fb-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d7fb-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9d7fb-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-224">ColumnName</span></span>|<span data-ttu-id="9d7fb-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9d7fb-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="9d7fb-227">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-227">String</span></span>|  
|<span data-ttu-id="9d7fb-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9d7fb-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9d7fb-229">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-229">String</span></span>|  
|<span data-ttu-id="9d7fb-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7fb-231">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-231">String</span></span>|  
|<span data-ttu-id="9d7fb-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-232">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-233">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-233">String</span></span>|  
|<span data-ttu-id="9d7fb-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-234">COLUMN_TYPE</span></span>|<span data-ttu-id="9d7fb-235">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-235">Int16</span></span>|  
|<span data-ttu-id="9d7fb-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-236">DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-237">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-237">Int16</span></span>|  
|<span data-ttu-id="9d7fb-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-238">TYPE_NAME</span></span>|<span data-ttu-id="9d7fb-239">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-239">String</span></span>|  
|<span data-ttu-id="9d7fb-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-240">COLUMN_SIZE</span></span>|<span data-ttu-id="9d7fb-241">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-241">Int32</span></span>|  
|<span data-ttu-id="9d7fb-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="9d7fb-243">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-243">Int32</span></span>|  
|<span data-ttu-id="9d7fb-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9d7fb-245">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-245">Int16</span></span>|  
|<span data-ttu-id="9d7fb-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9d7fb-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9d7fb-247">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-247">Int16</span></span>|  
|<span data-ttu-id="9d7fb-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-248">NULLABLE</span></span>|<span data-ttu-id="9d7fb-249">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-249">Int16</span></span>|  
|<span data-ttu-id="9d7fb-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-250">REMARKS</span></span>|<span data-ttu-id="9d7fb-251">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-251">String</span></span>|  
|<span data-ttu-id="9d7fb-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9d7fb-252">COLUMN_DEF</span></span>|<span data-ttu-id="9d7fb-253">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-253">String</span></span>|  
|<span data-ttu-id="9d7fb-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-255">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-255">Int16</span></span>|  
|<span data-ttu-id="9d7fb-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9d7fb-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9d7fb-257">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-257">Int16</span></span>|  
|<span data-ttu-id="9d7fb-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7fb-259">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-259">Int32</span></span>|  
|<span data-ttu-id="9d7fb-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-261">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-261">Int32</span></span>|  
|<span data-ttu-id="9d7fb-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-262">IS_NULLABLE</span></span>|<span data-ttu-id="9d7fb-263">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-263">String</span></span>|  
|<span data-ttu-id="9d7fb-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7fb-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9d7fb-265">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-265">String</span></span>|  
|<span data-ttu-id="9d7fb-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7fb-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9d7fb-267">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-267">String</span></span>|  
|<span data-ttu-id="9d7fb-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-269">Byte</span><span class="sxs-lookup"><span data-stu-id="9d7fb-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9d7fb-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d7fb-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9d7fb-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-271">ColumnName</span></span>|<span data-ttu-id="9d7fb-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9d7fb-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="9d7fb-274">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-274">String</span></span>|  
|<span data-ttu-id="9d7fb-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9d7fb-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9d7fb-276">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-276">String</span></span>|  
|<span data-ttu-id="9d7fb-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7fb-278">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-278">String</span></span>|  
|<span data-ttu-id="9d7fb-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-279">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-280">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-280">String</span></span>|  
|<span data-ttu-id="9d7fb-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-281">COLUMN_TYPE</span></span>|<span data-ttu-id="9d7fb-282">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-282">Int16</span></span>|  
|<span data-ttu-id="9d7fb-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-283">DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-284">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-284">Int16</span></span>|  
|<span data-ttu-id="9d7fb-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-285">TYPE_NAME</span></span>|<span data-ttu-id="9d7fb-286">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-286">String</span></span>|  
|<span data-ttu-id="9d7fb-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-287">COLUMN_SIZE</span></span>|<span data-ttu-id="9d7fb-288">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-288">Int32</span></span>|  
|<span data-ttu-id="9d7fb-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="9d7fb-290">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-290">Int32</span></span>|  
|<span data-ttu-id="9d7fb-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9d7fb-292">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-292">Int16</span></span>|  
|<span data-ttu-id="9d7fb-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9d7fb-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9d7fb-294">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-294">Int16</span></span>|  
|<span data-ttu-id="9d7fb-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-295">NULLABLE</span></span>|<span data-ttu-id="9d7fb-296">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-296">Int16</span></span>|  
|<span data-ttu-id="9d7fb-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-297">REMARKS</span></span>|<span data-ttu-id="9d7fb-298">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-298">String</span></span>|  
|<span data-ttu-id="9d7fb-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9d7fb-299">COLUMN_DEF</span></span>|<span data-ttu-id="9d7fb-300">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-300">String</span></span>|  
|<span data-ttu-id="9d7fb-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-302">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-302">Int16</span></span>|  
|<span data-ttu-id="9d7fb-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9d7fb-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9d7fb-304">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-304">Int16</span></span>|  
|<span data-ttu-id="9d7fb-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7fb-306">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-306">Int32</span></span>|  
|<span data-ttu-id="9d7fb-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-308">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-308">Int32</span></span>|  
|<span data-ttu-id="9d7fb-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-309">IS_NULLABLE</span></span>|<span data-ttu-id="9d7fb-310">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-310">String</span></span>|  
|<span data-ttu-id="9d7fb-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d7fb-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="9d7fb-312">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-312">String</span></span>|  
|<span data-ttu-id="9d7fb-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d7fb-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="9d7fb-314">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-314">String</span></span>|  
|<span data-ttu-id="9d7fb-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-316">Byte</span><span class="sxs-lookup"><span data-stu-id="9d7fb-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="9d7fb-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="9d7fb-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="9d7fb-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="9d7fb-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d7fb-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7fb-319">Tables</span></span>  
  
-   <span data-ttu-id="9d7fb-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7fb-320">Columns</span></span>  
  
-   <span data-ttu-id="9d7fb-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-321">Procedures</span></span>  
  
-   <span data-ttu-id="9d7fb-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d7fb-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9d7fb-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d7fb-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9d7fb-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d7fb-324">Views</span></span>  
  
-   <span data-ttu-id="9d7fb-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7fb-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="9d7fb-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="9d7fb-326">Tables and Views</span></span>  
  
|<span data-ttu-id="9d7fb-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-327">ColumnName</span></span>|<span data-ttu-id="9d7fb-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-330">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-330">String</span></span>|  
|<span data-ttu-id="9d7fb-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-331">TABLE_OWNER</span></span>|<span data-ttu-id="9d7fb-332">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-332">String</span></span>|  
|<span data-ttu-id="9d7fb-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-333">TABLE_NAME</span></span>|<span data-ttu-id="9d7fb-334">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-334">String</span></span>|  
|<span data-ttu-id="9d7fb-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-335">TABLE_TYPE</span></span>|<span data-ttu-id="9d7fb-336">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-336">String</span></span>|  
|<span data-ttu-id="9d7fb-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-337">REMARKS</span></span>|<span data-ttu-id="9d7fb-338">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d7fb-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7fb-339">Columns</span></span>  
  
|<span data-ttu-id="9d7fb-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-340">ColumnName</span></span>|<span data-ttu-id="9d7fb-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-343">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-343">String</span></span>|  
|<span data-ttu-id="9d7fb-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-344">TABLE_OWNER</span></span>|<span data-ttu-id="9d7fb-345">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-345">String</span></span>|  
|<span data-ttu-id="9d7fb-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-346">TABLE_NAME</span></span>|<span data-ttu-id="9d7fb-347">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-347">String</span></span>|  
|<span data-ttu-id="9d7fb-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-348">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-349">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-349">String</span></span>|  
|<span data-ttu-id="9d7fb-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-350">DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-351">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-351">Int16</span></span>|  
|<span data-ttu-id="9d7fb-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-352">TYPE_NAME</span></span>|<span data-ttu-id="9d7fb-353">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-353">String</span></span>|  
|<span data-ttu-id="9d7fb-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-354">PRECISION</span></span>|<span data-ttu-id="9d7fb-355">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-355">Int32</span></span>|  
|<span data-ttu-id="9d7fb-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-356">LENGTH</span></span>|<span data-ttu-id="9d7fb-357">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-357">Int32</span></span>|  
|<span data-ttu-id="9d7fb-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-358">SCALE</span></span>|<span data-ttu-id="9d7fb-359">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-359">Int16</span></span>|  
|<span data-ttu-id="9d7fb-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="9d7fb-360">RADIX</span></span>|<span data-ttu-id="9d7fb-361">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-361">Int16</span></span>|  
|<span data-ttu-id="9d7fb-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-362">NULLABLE</span></span>|<span data-ttu-id="9d7fb-363">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-363">Int16</span></span>|  
|<span data-ttu-id="9d7fb-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-364">REMARKS</span></span>|<span data-ttu-id="9d7fb-365">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-365">String</span></span>|  
|<span data-ttu-id="9d7fb-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-367">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d7fb-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-368">Procedures</span></span>  
  
|<span data-ttu-id="9d7fb-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-369">ColumnName</span></span>|<span data-ttu-id="9d7fb-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-372">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-372">String</span></span>|  
|<span data-ttu-id="9d7fb-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9d7fb-374">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-374">String</span></span>|  
|<span data-ttu-id="9d7fb-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7fb-376">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-376">String</span></span>|  
|<span data-ttu-id="9d7fb-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9d7fb-378">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-378">Int16</span></span>|  
|<span data-ttu-id="9d7fb-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9d7fb-380">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-380">Int16</span></span>|  
|<span data-ttu-id="9d7fb-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9d7fb-382">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-382">Int16</span></span>|  
|<span data-ttu-id="9d7fb-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-383">REMARKS</span></span>|<span data-ttu-id="9d7fb-384">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-384">String</span></span>|  
|<span data-ttu-id="9d7fb-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d7fb-386">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9d7fb-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d7fb-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9d7fb-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-388">ColumnName</span></span>|<span data-ttu-id="9d7fb-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-391">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-391">String</span></span>|  
|<span data-ttu-id="9d7fb-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9d7fb-393">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-393">String</span></span>|  
|<span data-ttu-id="9d7fb-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7fb-395">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-395">String</span></span>|  
|<span data-ttu-id="9d7fb-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-396">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-397">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-397">String</span></span>|  
|<span data-ttu-id="9d7fb-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-398">COLUMN_TYPE</span></span>|<span data-ttu-id="9d7fb-399">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-399">Int16</span></span>|  
|<span data-ttu-id="9d7fb-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-400">DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-401">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-401">Int16</span></span>|  
|<span data-ttu-id="9d7fb-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-402">TYPE_NAME</span></span>|<span data-ttu-id="9d7fb-403">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-403">String</span></span>|  
|<span data-ttu-id="9d7fb-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-404">PRECISION</span></span>|<span data-ttu-id="9d7fb-405">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-405">Int32</span></span>|  
|<span data-ttu-id="9d7fb-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-406">LENGTH</span></span>|<span data-ttu-id="9d7fb-407">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-407">Int32</span></span>|  
|<span data-ttu-id="9d7fb-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-408">SCALE</span></span>|<span data-ttu-id="9d7fb-409">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-409">Int16</span></span>|  
|<span data-ttu-id="9d7fb-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="9d7fb-410">RADIX</span></span>|<span data-ttu-id="9d7fb-411">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-411">Int16</span></span>|  
|<span data-ttu-id="9d7fb-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-412">NULLABLE</span></span>|<span data-ttu-id="9d7fb-413">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-413">Int16</span></span>|  
|<span data-ttu-id="9d7fb-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-414">REMARKS</span></span>|<span data-ttu-id="9d7fb-415">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-415">String</span></span>|  
|<span data-ttu-id="9d7fb-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9d7fb-416">OVERLOAD</span></span>|<span data-ttu-id="9d7fb-417">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-417">Int32</span></span>|  
|<span data-ttu-id="9d7fb-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-419">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="9d7fb-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="9d7fb-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="9d7fb-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d7fb-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d7fb-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d7fb-422">Tables</span></span>  
  
-   <span data-ttu-id="9d7fb-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d7fb-423">Indexes</span></span>  
  
-   <span data-ttu-id="9d7fb-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7fb-424">Columns</span></span>  
  
-   <span data-ttu-id="9d7fb-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-425">Procedures</span></span>  
  
-   <span data-ttu-id="9d7fb-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d7fb-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9d7fb-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d7fb-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9d7fb-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d7fb-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="9d7fb-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="9d7fb-429">Tables and Views</span></span>  
  
|<span data-ttu-id="9d7fb-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-430">ColumnName</span></span>|<span data-ttu-id="9d7fb-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-433">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-433">String</span></span>|  
|<span data-ttu-id="9d7fb-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-434">TABLE_OWNER</span></span>|<span data-ttu-id="9d7fb-435">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-435">String</span></span>|  
|<span data-ttu-id="9d7fb-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-436">TABLE_NAME</span></span>|<span data-ttu-id="9d7fb-437">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-437">String</span></span>|  
|<span data-ttu-id="9d7fb-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-438">TABLE_TYPE</span></span>|<span data-ttu-id="9d7fb-439">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-439">String</span></span>|  
|<span data-ttu-id="9d7fb-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-440">REMARKS</span></span>|<span data-ttu-id="9d7fb-441">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d7fb-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d7fb-442">Columns</span></span>  
  
|<span data-ttu-id="9d7fb-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-443">ColumnName</span></span>|<span data-ttu-id="9d7fb-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-446">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-446">String</span></span>|  
|<span data-ttu-id="9d7fb-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-447">TABLE_OWNER</span></span>|<span data-ttu-id="9d7fb-448">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-448">String</span></span>|  
|<span data-ttu-id="9d7fb-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-449">TABLE_NAME</span></span>|<span data-ttu-id="9d7fb-450">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-450">String</span></span>|  
|<span data-ttu-id="9d7fb-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-451">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-452">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-452">String</span></span>|  
|<span data-ttu-id="9d7fb-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-453">DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-454">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-454">Int16</span></span>|  
|<span data-ttu-id="9d7fb-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-455">TYPE_NAME</span></span>|<span data-ttu-id="9d7fb-456">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-456">String</span></span>|  
|<span data-ttu-id="9d7fb-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-457">PRECISION</span></span>|<span data-ttu-id="9d7fb-458">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-458">Int32</span></span>|  
|<span data-ttu-id="9d7fb-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-459">LENGTH</span></span>|<span data-ttu-id="9d7fb-460">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-460">Int32</span></span>|  
|<span data-ttu-id="9d7fb-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-461">SCALE</span></span>|<span data-ttu-id="9d7fb-462">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-462">Int16</span></span>|  
|<span data-ttu-id="9d7fb-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="9d7fb-463">RADIX</span></span>|<span data-ttu-id="9d7fb-464">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-464">Int16</span></span>|  
|<span data-ttu-id="9d7fb-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-465">NULLABLE</span></span>|<span data-ttu-id="9d7fb-466">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-466">Int16</span></span>|  
|<span data-ttu-id="9d7fb-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-467">REMARKS</span></span>|<span data-ttu-id="9d7fb-468">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-468">String</span></span>|  
|<span data-ttu-id="9d7fb-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-470">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d7fb-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d7fb-471">Procedures</span></span>  
  
|<span data-ttu-id="9d7fb-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-472">ColumnName</span></span>|<span data-ttu-id="9d7fb-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-475">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-475">String</span></span>|  
|<span data-ttu-id="9d7fb-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9d7fb-477">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-477">String</span></span>|  
|<span data-ttu-id="9d7fb-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7fb-479">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-479">String</span></span>|  
|<span data-ttu-id="9d7fb-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="9d7fb-481">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-481">Int16</span></span>|  
|<span data-ttu-id="9d7fb-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="9d7fb-483">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-483">Int16</span></span>|  
|<span data-ttu-id="9d7fb-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="9d7fb-485">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-485">Int16</span></span>|  
|<span data-ttu-id="9d7fb-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-486">REMARKS</span></span>|<span data-ttu-id="9d7fb-487">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-487">String</span></span>|  
|<span data-ttu-id="9d7fb-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d7fb-489">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9d7fb-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d7fb-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9d7fb-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-491">ColumnName</span></span>|<span data-ttu-id="9d7fb-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="9d7fb-494">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-494">String</span></span>|  
|<span data-ttu-id="9d7fb-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d7fb-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="9d7fb-496">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-496">String</span></span>|  
|<span data-ttu-id="9d7fb-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7fb-498">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-498">String</span></span>|  
|<span data-ttu-id="9d7fb-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-499">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-500">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-500">String</span></span>|  
|<span data-ttu-id="9d7fb-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-501">COLUMN_TYPE</span></span>|<span data-ttu-id="9d7fb-502">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-502">Int16</span></span>|  
|<span data-ttu-id="9d7fb-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-503">DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-504">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-504">Int16</span></span>|  
|<span data-ttu-id="9d7fb-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-505">TYPE_NAME</span></span>|<span data-ttu-id="9d7fb-506">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-506">String</span></span>|  
|<span data-ttu-id="9d7fb-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-507">PRECISION</span></span>|<span data-ttu-id="9d7fb-508">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-508">Int32</span></span>|  
|<span data-ttu-id="9d7fb-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-509">LENGTH</span></span>|<span data-ttu-id="9d7fb-510">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-510">Int32</span></span>|  
|<span data-ttu-id="9d7fb-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-511">SCALE</span></span>|<span data-ttu-id="9d7fb-512">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-512">Int16</span></span>|  
|<span data-ttu-id="9d7fb-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="9d7fb-513">RADIX</span></span>|<span data-ttu-id="9d7fb-514">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-514">Int16</span></span>|  
|<span data-ttu-id="9d7fb-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-515">NULLABLE</span></span>|<span data-ttu-id="9d7fb-516">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-516">Int16</span></span>|  
|<span data-ttu-id="9d7fb-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-517">REMARKS</span></span>|<span data-ttu-id="9d7fb-518">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-518">String</span></span>|  
|<span data-ttu-id="9d7fb-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9d7fb-519">OVERLOAD</span></span>|<span data-ttu-id="9d7fb-520">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-520">Int32</span></span>|  
|<span data-ttu-id="9d7fb-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-522">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9d7fb-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d7fb-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9d7fb-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d7fb-524">ColumnName</span></span>|<span data-ttu-id="9d7fb-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d7fb-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="9d7fb-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="9d7fb-527">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-527">String</span></span>|  
|<span data-ttu-id="9d7fb-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="9d7fb-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="9d7fb-529">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-529">String</span></span>|  
|<span data-ttu-id="9d7fb-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d7fb-531">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-531">String</span></span>|  
|<span data-ttu-id="9d7fb-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-532">COLUMN_NAME</span></span>|<span data-ttu-id="9d7fb-533">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-533">String</span></span>|  
|<span data-ttu-id="9d7fb-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-534">COLUMN_TYPE</span></span>|<span data-ttu-id="9d7fb-535">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-535">Int16</span></span>|  
|<span data-ttu-id="9d7fb-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-536">DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-537">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-537">Int16</span></span>|  
|<span data-ttu-id="9d7fb-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d7fb-538">TYPE_NAME</span></span>|<span data-ttu-id="9d7fb-539">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-539">String</span></span>|  
|<span data-ttu-id="9d7fb-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-540">COLUMN_SIZE</span></span>|<span data-ttu-id="9d7fb-541">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-541">Int32</span></span>|  
|<span data-ttu-id="9d7fb-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="9d7fb-543">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-543">Int32</span></span>|  
|<span data-ttu-id="9d7fb-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="9d7fb-545">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-545">Int16</span></span>|  
|<span data-ttu-id="9d7fb-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="9d7fb-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="9d7fb-547">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-547">Int16</span></span>|  
|<span data-ttu-id="9d7fb-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-548">NULLABLE</span></span>|<span data-ttu-id="9d7fb-549">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-549">Int16</span></span>|  
|<span data-ttu-id="9d7fb-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="9d7fb-550">REMARKS</span></span>|<span data-ttu-id="9d7fb-551">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-551">String</span></span>|  
|<span data-ttu-id="9d7fb-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="9d7fb-552">COLUMN_DEF</span></span>|<span data-ttu-id="9d7fb-553">String</span><span class="sxs-lookup"><span data-stu-id="9d7fb-553">String</span></span>|  
|<span data-ttu-id="9d7fb-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="9d7fb-555">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-555">Int16</span></span>|  
|<span data-ttu-id="9d7fb-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="9d7fb-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="9d7fb-557">Int16</span><span class="sxs-lookup"><span data-stu-id="9d7fb-557">Int16</span></span>|  
|<span data-ttu-id="9d7fb-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d7fb-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="9d7fb-559">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-559">Int32</span></span>|  
|<span data-ttu-id="9d7fb-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d7fb-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d7fb-561">Int32</span><span class="sxs-lookup"><span data-stu-id="9d7fb-561">Int32</span></span>|  
|<span data-ttu-id="9d7fb-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d7fb-562">IS_NULLABLE</span></span>|<span data-ttu-id="9d7fb-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="9d7fb-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d7fb-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d7fb-564">See Also</span></span>  
 [<span data-ttu-id="9d7fb-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9d7fb-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
