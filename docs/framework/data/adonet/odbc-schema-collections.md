---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 36d0859b897bfcea33803c219ade14722ed90421
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="74ef1-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="74ef1-102">ODBC Schema Collections</span></span>
<span data-ttu-id="74ef1-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="74ef1-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="74ef1-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="74ef1-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="74ef1-105">Il Driver ODBC di Microsoft SQL Server supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="74ef1-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="74ef1-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="74ef1-106">Tables</span></span>  
  
-   <span data-ttu-id="74ef1-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="74ef1-107">Indexes</span></span>  
  
-   <span data-ttu-id="74ef1-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="74ef1-108">Columns</span></span>  
  
-   <span data-ttu-id="74ef1-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="74ef1-109">Procedures</span></span>  
  
-   <span data-ttu-id="74ef1-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74ef1-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="74ef1-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74ef1-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="74ef1-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="74ef1-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="74ef1-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="74ef1-113">Tables and Views</span></span>  
  
|<span data-ttu-id="74ef1-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-114">ColumnName</span></span>|<span data-ttu-id="74ef1-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="74ef1-116">TABLE_CAT</span></span>|<span data-ttu-id="74ef1-117">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-117">String</span></span>|  
|<span data-ttu-id="74ef1-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74ef1-118">TABLE_SCHEM</span></span>|<span data-ttu-id="74ef1-119">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-119">String</span></span>|  
|<span data-ttu-id="74ef1-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-120">TABLE_NAME</span></span>|<span data-ttu-id="74ef1-121">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-121">String</span></span>|  
|<span data-ttu-id="74ef1-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-122">TABLE_TYPE</span></span>|<span data-ttu-id="74ef1-123">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-123">String</span></span>|  
|<span data-ttu-id="74ef1-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-124">REMARKS</span></span>|<span data-ttu-id="74ef1-125">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="74ef1-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="74ef1-126">Indexes</span></span>  
  
|<span data-ttu-id="74ef1-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-127">ColumnName</span></span>|<span data-ttu-id="74ef1-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="74ef1-129">TABLE_CAT</span></span>|<span data-ttu-id="74ef1-130">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-130">String</span></span>|  
|<span data-ttu-id="74ef1-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74ef1-131">TABLE_SCHEM</span></span>|<span data-ttu-id="74ef1-132">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-132">String</span></span>|  
|<span data-ttu-id="74ef1-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-133">TABLE_NAME</span></span>|<span data-ttu-id="74ef1-134">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-134">String</span></span>|  
|<span data-ttu-id="74ef1-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="74ef1-135">NON_UNIQUE</span></span>|<span data-ttu-id="74ef1-136">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-136">Int16</span></span>|  
|<span data-ttu-id="74ef1-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="74ef1-138">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-138">String</span></span>|  
|<span data-ttu-id="74ef1-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-139">INDEX_NAME</span></span>|<span data-ttu-id="74ef1-140">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-140">String</span></span>|  
|<span data-ttu-id="74ef1-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-141">TYPE</span></span>|<span data-ttu-id="74ef1-142">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-142">Int16</span></span>|  
|<span data-ttu-id="74ef1-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-144">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-144">Int16</span></span>|  
|<span data-ttu-id="74ef1-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-145">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-146">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-146">String</span></span>|  
|<span data-ttu-id="74ef1-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="74ef1-147">ASC_OR_DESC</span></span>|<span data-ttu-id="74ef1-148">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-148">String</span></span>|  
|<span data-ttu-id="74ef1-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="74ef1-149">CARDINATLITY</span></span>|<span data-ttu-id="74ef1-150">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-150">Int32</span></span>|  
|<span data-ttu-id="74ef1-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="74ef1-151">PAGES</span></span>|<span data-ttu-id="74ef1-152">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-152">Int32</span></span>|  
|<span data-ttu-id="74ef1-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-153">FILTER_CONDITION</span></span>|<span data-ttu-id="74ef1-154">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-154">String</span></span>|  
|<span data-ttu-id="74ef1-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="74ef1-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="74ef1-156">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-156">String</span></span>|  
|<span data-ttu-id="74ef1-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="74ef1-158">Byte</span><span class="sxs-lookup"><span data-stu-id="74ef1-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="74ef1-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="74ef1-159">Columns</span></span>  
  
|<span data-ttu-id="74ef1-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-160">ColumnName</span></span>|<span data-ttu-id="74ef1-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="74ef1-162">TABLE_CAT</span></span>|<span data-ttu-id="74ef1-163">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-163">String</span></span>|  
|<span data-ttu-id="74ef1-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74ef1-164">TABLE_SCHEM</span></span>|<span data-ttu-id="74ef1-165">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-165">String</span></span>|  
|<span data-ttu-id="74ef1-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-166">TABLE_NAME</span></span>|<span data-ttu-id="74ef1-167">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-167">String</span></span>|  
|<span data-ttu-id="74ef1-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-168">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-169">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-169">String</span></span>|  
|<span data-ttu-id="74ef1-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-170">DATA_TYPE</span></span>|<span data-ttu-id="74ef1-171">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-171">Int16</span></span>|  
|<span data-ttu-id="74ef1-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-172">TYPE_NAME</span></span>|<span data-ttu-id="74ef1-173">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-173">String</span></span>|  
|<span data-ttu-id="74ef1-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="74ef1-174">COLUMN_SIZE</span></span>|<span data-ttu-id="74ef1-175">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-175">Int32</span></span>|  
|<span data-ttu-id="74ef1-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="74ef1-177">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-177">Int32</span></span>|  
|<span data-ttu-id="74ef1-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="74ef1-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="74ef1-179">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-179">Int16</span></span>|  
|<span data-ttu-id="74ef1-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="74ef1-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="74ef1-181">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-181">Int16</span></span>|  
|<span data-ttu-id="74ef1-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-182">NULLABLE</span></span>|<span data-ttu-id="74ef1-183">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-183">Int16</span></span>|  
|<span data-ttu-id="74ef1-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-184">REMARKS</span></span>|<span data-ttu-id="74ef1-185">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-185">String</span></span>|  
|<span data-ttu-id="74ef1-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="74ef1-186">COLUMN_DEF</span></span>|<span data-ttu-id="74ef1-187">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-187">String</span></span>|  
|<span data-ttu-id="74ef1-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="74ef1-189">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-189">Int16</span></span>|  
|<span data-ttu-id="74ef1-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="74ef1-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="74ef1-191">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-191">Int16</span></span>|  
|<span data-ttu-id="74ef1-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="74ef1-193">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-193">Int32</span></span>|  
|<span data-ttu-id="74ef1-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-195">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-195">Int32</span></span>|  
|<span data-ttu-id="74ef1-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-196">IS_NULLABLE</span></span>|<span data-ttu-id="74ef1-197">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-197">String</span></span>|  
|<span data-ttu-id="74ef1-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="74ef1-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="74ef1-199">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-199">String</span></span>|  
|<span data-ttu-id="74ef1-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="74ef1-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="74ef1-201">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-201">String</span></span>|  
|<span data-ttu-id="74ef1-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="74ef1-203">Byte</span><span class="sxs-lookup"><span data-stu-id="74ef1-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="74ef1-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="74ef1-204">Procedures</span></span>  
  
|<span data-ttu-id="74ef1-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-205">ColumnName</span></span>|<span data-ttu-id="74ef1-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="74ef1-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="74ef1-208">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-208">String</span></span>|  
|<span data-ttu-id="74ef1-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74ef1-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="74ef1-210">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-210">String</span></span>|  
|<span data-ttu-id="74ef1-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="74ef1-212">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-212">String</span></span>|  
|<span data-ttu-id="74ef1-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74ef1-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="74ef1-214">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-214">Int32</span></span>|  
|<span data-ttu-id="74ef1-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74ef1-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="74ef1-216">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-216">Int32</span></span>|  
|<span data-ttu-id="74ef1-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="74ef1-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="74ef1-218">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-218">Int32</span></span>|  
|<span data-ttu-id="74ef1-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-219">REMARKS</span></span>|<span data-ttu-id="74ef1-220">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-220">String</span></span>|  
|<span data-ttu-id="74ef1-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="74ef1-222">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="74ef1-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74ef1-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="74ef1-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-224">ColumnName</span></span>|<span data-ttu-id="74ef1-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="74ef1-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="74ef1-227">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-227">String</span></span>|  
|<span data-ttu-id="74ef1-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74ef1-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="74ef1-229">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-229">String</span></span>|  
|<span data-ttu-id="74ef1-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="74ef1-231">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-231">String</span></span>|  
|<span data-ttu-id="74ef1-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-232">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-233">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-233">String</span></span>|  
|<span data-ttu-id="74ef1-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-234">COLUMN_TYPE</span></span>|<span data-ttu-id="74ef1-235">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-235">Int16</span></span>|  
|<span data-ttu-id="74ef1-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-236">DATA_TYPE</span></span>|<span data-ttu-id="74ef1-237">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-237">Int16</span></span>|  
|<span data-ttu-id="74ef1-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-238">TYPE_NAME</span></span>|<span data-ttu-id="74ef1-239">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-239">String</span></span>|  
|<span data-ttu-id="74ef1-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="74ef1-240">COLUMN_SIZE</span></span>|<span data-ttu-id="74ef1-241">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-241">Int32</span></span>|  
|<span data-ttu-id="74ef1-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="74ef1-243">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-243">Int32</span></span>|  
|<span data-ttu-id="74ef1-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="74ef1-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="74ef1-245">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-245">Int16</span></span>|  
|<span data-ttu-id="74ef1-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="74ef1-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="74ef1-247">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-247">Int16</span></span>|  
|<span data-ttu-id="74ef1-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-248">NULLABLE</span></span>|<span data-ttu-id="74ef1-249">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-249">Int16</span></span>|  
|<span data-ttu-id="74ef1-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-250">REMARKS</span></span>|<span data-ttu-id="74ef1-251">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-251">String</span></span>|  
|<span data-ttu-id="74ef1-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="74ef1-252">COLUMN_DEF</span></span>|<span data-ttu-id="74ef1-253">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-253">String</span></span>|  
|<span data-ttu-id="74ef1-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="74ef1-255">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-255">Int16</span></span>|  
|<span data-ttu-id="74ef1-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="74ef1-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="74ef1-257">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-257">Int16</span></span>|  
|<span data-ttu-id="74ef1-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="74ef1-259">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-259">Int32</span></span>|  
|<span data-ttu-id="74ef1-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-261">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-261">Int32</span></span>|  
|<span data-ttu-id="74ef1-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-262">IS_NULLABLE</span></span>|<span data-ttu-id="74ef1-263">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-263">String</span></span>|  
|<span data-ttu-id="74ef1-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="74ef1-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="74ef1-265">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-265">String</span></span>|  
|<span data-ttu-id="74ef1-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="74ef1-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="74ef1-267">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-267">String</span></span>|  
|<span data-ttu-id="74ef1-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="74ef1-269">Byte</span><span class="sxs-lookup"><span data-stu-id="74ef1-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="74ef1-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74ef1-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="74ef1-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-271">ColumnName</span></span>|<span data-ttu-id="74ef1-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="74ef1-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="74ef1-274">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-274">String</span></span>|  
|<span data-ttu-id="74ef1-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74ef1-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="74ef1-276">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-276">String</span></span>|  
|<span data-ttu-id="74ef1-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="74ef1-278">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-278">String</span></span>|  
|<span data-ttu-id="74ef1-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-279">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-280">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-280">String</span></span>|  
|<span data-ttu-id="74ef1-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-281">COLUMN_TYPE</span></span>|<span data-ttu-id="74ef1-282">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-282">Int16</span></span>|  
|<span data-ttu-id="74ef1-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-283">DATA_TYPE</span></span>|<span data-ttu-id="74ef1-284">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-284">Int16</span></span>|  
|<span data-ttu-id="74ef1-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-285">TYPE_NAME</span></span>|<span data-ttu-id="74ef1-286">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-286">String</span></span>|  
|<span data-ttu-id="74ef1-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="74ef1-287">COLUMN_SIZE</span></span>|<span data-ttu-id="74ef1-288">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-288">Int32</span></span>|  
|<span data-ttu-id="74ef1-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="74ef1-290">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-290">Int32</span></span>|  
|<span data-ttu-id="74ef1-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="74ef1-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="74ef1-292">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-292">Int16</span></span>|  
|<span data-ttu-id="74ef1-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="74ef1-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="74ef1-294">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-294">Int16</span></span>|  
|<span data-ttu-id="74ef1-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-295">NULLABLE</span></span>|<span data-ttu-id="74ef1-296">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-296">Int16</span></span>|  
|<span data-ttu-id="74ef1-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-297">REMARKS</span></span>|<span data-ttu-id="74ef1-298">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-298">String</span></span>|  
|<span data-ttu-id="74ef1-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="74ef1-299">COLUMN_DEF</span></span>|<span data-ttu-id="74ef1-300">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-300">String</span></span>|  
|<span data-ttu-id="74ef1-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="74ef1-302">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-302">Int16</span></span>|  
|<span data-ttu-id="74ef1-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="74ef1-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="74ef1-304">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-304">Int16</span></span>|  
|<span data-ttu-id="74ef1-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="74ef1-306">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-306">Int32</span></span>|  
|<span data-ttu-id="74ef1-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-308">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-308">Int32</span></span>|  
|<span data-ttu-id="74ef1-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-309">IS_NULLABLE</span></span>|<span data-ttu-id="74ef1-310">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-310">String</span></span>|  
|<span data-ttu-id="74ef1-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="74ef1-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="74ef1-312">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-312">String</span></span>|  
|<span data-ttu-id="74ef1-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="74ef1-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="74ef1-314">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-314">String</span></span>|  
|<span data-ttu-id="74ef1-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="74ef1-316">Byte</span><span class="sxs-lookup"><span data-stu-id="74ef1-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="74ef1-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="74ef1-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="74ef1-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="74ef1-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="74ef1-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="74ef1-319">Tables</span></span>  
  
-   <span data-ttu-id="74ef1-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="74ef1-320">Columns</span></span>  
  
-   <span data-ttu-id="74ef1-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="74ef1-321">Procedures</span></span>  
  
-   <span data-ttu-id="74ef1-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74ef1-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="74ef1-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74ef1-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="74ef1-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="74ef1-324">Views</span></span>  
  
-   <span data-ttu-id="74ef1-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="74ef1-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="74ef1-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="74ef1-326">Tables and Views</span></span>  
  
|<span data-ttu-id="74ef1-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-327">ColumnName</span></span>|<span data-ttu-id="74ef1-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="74ef1-330">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-330">String</span></span>|  
|<span data-ttu-id="74ef1-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74ef1-331">TABLE_OWNER</span></span>|<span data-ttu-id="74ef1-332">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-332">String</span></span>|  
|<span data-ttu-id="74ef1-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-333">TABLE_NAME</span></span>|<span data-ttu-id="74ef1-334">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-334">String</span></span>|  
|<span data-ttu-id="74ef1-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-335">TABLE_TYPE</span></span>|<span data-ttu-id="74ef1-336">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-336">String</span></span>|  
|<span data-ttu-id="74ef1-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-337">REMARKS</span></span>|<span data-ttu-id="74ef1-338">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="74ef1-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="74ef1-339">Columns</span></span>  
  
|<span data-ttu-id="74ef1-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-340">ColumnName</span></span>|<span data-ttu-id="74ef1-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="74ef1-343">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-343">String</span></span>|  
|<span data-ttu-id="74ef1-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74ef1-344">TABLE_OWNER</span></span>|<span data-ttu-id="74ef1-345">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-345">String</span></span>|  
|<span data-ttu-id="74ef1-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-346">TABLE_NAME</span></span>|<span data-ttu-id="74ef1-347">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-347">String</span></span>|  
|<span data-ttu-id="74ef1-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-348">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-349">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-349">String</span></span>|  
|<span data-ttu-id="74ef1-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-350">DATA_TYPE</span></span>|<span data-ttu-id="74ef1-351">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-351">Int16</span></span>|  
|<span data-ttu-id="74ef1-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-352">TYPE_NAME</span></span>|<span data-ttu-id="74ef1-353">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-353">String</span></span>|  
|<span data-ttu-id="74ef1-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="74ef1-354">PRECISION</span></span>|<span data-ttu-id="74ef1-355">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-355">Int32</span></span>|  
|<span data-ttu-id="74ef1-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-356">LENGTH</span></span>|<span data-ttu-id="74ef1-357">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-357">Int32</span></span>|  
|<span data-ttu-id="74ef1-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="74ef1-358">SCALE</span></span>|<span data-ttu-id="74ef1-359">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-359">Int16</span></span>|  
|<span data-ttu-id="74ef1-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="74ef1-360">RADIX</span></span>|<span data-ttu-id="74ef1-361">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-361">Int16</span></span>|  
|<span data-ttu-id="74ef1-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-362">NULLABLE</span></span>|<span data-ttu-id="74ef1-363">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-363">Int16</span></span>|  
|<span data-ttu-id="74ef1-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-364">REMARKS</span></span>|<span data-ttu-id="74ef1-365">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-365">String</span></span>|  
|<span data-ttu-id="74ef1-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-367">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="74ef1-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="74ef1-368">Procedures</span></span>  
  
|<span data-ttu-id="74ef1-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-369">ColumnName</span></span>|<span data-ttu-id="74ef1-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="74ef1-372">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-372">String</span></span>|  
|<span data-ttu-id="74ef1-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74ef1-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="74ef1-374">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-374">String</span></span>|  
|<span data-ttu-id="74ef1-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="74ef1-376">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-376">String</span></span>|  
|<span data-ttu-id="74ef1-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74ef1-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="74ef1-378">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-378">Int16</span></span>|  
|<span data-ttu-id="74ef1-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74ef1-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="74ef1-380">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-380">Int16</span></span>|  
|<span data-ttu-id="74ef1-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="74ef1-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="74ef1-382">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-382">Int16</span></span>|  
|<span data-ttu-id="74ef1-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-383">REMARKS</span></span>|<span data-ttu-id="74ef1-384">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-384">String</span></span>|  
|<span data-ttu-id="74ef1-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="74ef1-386">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="74ef1-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74ef1-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="74ef1-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-388">ColumnName</span></span>|<span data-ttu-id="74ef1-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="74ef1-391">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-391">String</span></span>|  
|<span data-ttu-id="74ef1-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74ef1-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="74ef1-393">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-393">String</span></span>|  
|<span data-ttu-id="74ef1-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="74ef1-395">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-395">String</span></span>|  
|<span data-ttu-id="74ef1-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-396">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-397">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-397">String</span></span>|  
|<span data-ttu-id="74ef1-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-398">COLUMN_TYPE</span></span>|<span data-ttu-id="74ef1-399">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-399">Int16</span></span>|  
|<span data-ttu-id="74ef1-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-400">DATA_TYPE</span></span>|<span data-ttu-id="74ef1-401">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-401">Int16</span></span>|  
|<span data-ttu-id="74ef1-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-402">TYPE_NAME</span></span>|<span data-ttu-id="74ef1-403">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-403">String</span></span>|  
|<span data-ttu-id="74ef1-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="74ef1-404">PRECISION</span></span>|<span data-ttu-id="74ef1-405">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-405">Int32</span></span>|  
|<span data-ttu-id="74ef1-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-406">LENGTH</span></span>|<span data-ttu-id="74ef1-407">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-407">Int32</span></span>|  
|<span data-ttu-id="74ef1-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="74ef1-408">SCALE</span></span>|<span data-ttu-id="74ef1-409">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-409">Int16</span></span>|  
|<span data-ttu-id="74ef1-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="74ef1-410">RADIX</span></span>|<span data-ttu-id="74ef1-411">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-411">Int16</span></span>|  
|<span data-ttu-id="74ef1-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-412">NULLABLE</span></span>|<span data-ttu-id="74ef1-413">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-413">Int16</span></span>|  
|<span data-ttu-id="74ef1-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-414">REMARKS</span></span>|<span data-ttu-id="74ef1-415">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-415">String</span></span>|  
|<span data-ttu-id="74ef1-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="74ef1-416">OVERLOAD</span></span>|<span data-ttu-id="74ef1-417">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-417">Int32</span></span>|  
|<span data-ttu-id="74ef1-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-419">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="74ef1-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="74ef1-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="74ef1-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="74ef1-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="74ef1-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="74ef1-422">Tables</span></span>  
  
-   <span data-ttu-id="74ef1-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="74ef1-423">Indexes</span></span>  
  
-   <span data-ttu-id="74ef1-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="74ef1-424">Columns</span></span>  
  
-   <span data-ttu-id="74ef1-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="74ef1-425">Procedures</span></span>  
  
-   <span data-ttu-id="74ef1-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74ef1-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="74ef1-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74ef1-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="74ef1-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="74ef1-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="74ef1-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="74ef1-429">Tables and Views</span></span>  
  
|<span data-ttu-id="74ef1-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-430">ColumnName</span></span>|<span data-ttu-id="74ef1-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="74ef1-433">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-433">String</span></span>|  
|<span data-ttu-id="74ef1-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74ef1-434">TABLE_OWNER</span></span>|<span data-ttu-id="74ef1-435">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-435">String</span></span>|  
|<span data-ttu-id="74ef1-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-436">TABLE_NAME</span></span>|<span data-ttu-id="74ef1-437">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-437">String</span></span>|  
|<span data-ttu-id="74ef1-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-438">TABLE_TYPE</span></span>|<span data-ttu-id="74ef1-439">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-439">String</span></span>|  
|<span data-ttu-id="74ef1-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-440">REMARKS</span></span>|<span data-ttu-id="74ef1-441">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="74ef1-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="74ef1-442">Columns</span></span>  
  
|<span data-ttu-id="74ef1-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-443">ColumnName</span></span>|<span data-ttu-id="74ef1-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="74ef1-446">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-446">String</span></span>|  
|<span data-ttu-id="74ef1-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74ef1-447">TABLE_OWNER</span></span>|<span data-ttu-id="74ef1-448">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-448">String</span></span>|  
|<span data-ttu-id="74ef1-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-449">TABLE_NAME</span></span>|<span data-ttu-id="74ef1-450">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-450">String</span></span>|  
|<span data-ttu-id="74ef1-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-451">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-452">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-452">String</span></span>|  
|<span data-ttu-id="74ef1-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-453">DATA_TYPE</span></span>|<span data-ttu-id="74ef1-454">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-454">Int16</span></span>|  
|<span data-ttu-id="74ef1-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-455">TYPE_NAME</span></span>|<span data-ttu-id="74ef1-456">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-456">String</span></span>|  
|<span data-ttu-id="74ef1-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="74ef1-457">PRECISION</span></span>|<span data-ttu-id="74ef1-458">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-458">Int32</span></span>|  
|<span data-ttu-id="74ef1-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-459">LENGTH</span></span>|<span data-ttu-id="74ef1-460">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-460">Int32</span></span>|  
|<span data-ttu-id="74ef1-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="74ef1-461">SCALE</span></span>|<span data-ttu-id="74ef1-462">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-462">Int16</span></span>|  
|<span data-ttu-id="74ef1-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="74ef1-463">RADIX</span></span>|<span data-ttu-id="74ef1-464">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-464">Int16</span></span>|  
|<span data-ttu-id="74ef1-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-465">NULLABLE</span></span>|<span data-ttu-id="74ef1-466">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-466">Int16</span></span>|  
|<span data-ttu-id="74ef1-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-467">REMARKS</span></span>|<span data-ttu-id="74ef1-468">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-468">String</span></span>|  
|<span data-ttu-id="74ef1-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-470">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="74ef1-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="74ef1-471">Procedures</span></span>  
  
|<span data-ttu-id="74ef1-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-472">ColumnName</span></span>|<span data-ttu-id="74ef1-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="74ef1-475">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-475">String</span></span>|  
|<span data-ttu-id="74ef1-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74ef1-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="74ef1-477">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-477">String</span></span>|  
|<span data-ttu-id="74ef1-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="74ef1-479">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-479">String</span></span>|  
|<span data-ttu-id="74ef1-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74ef1-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="74ef1-481">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-481">Int16</span></span>|  
|<span data-ttu-id="74ef1-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="74ef1-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="74ef1-483">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-483">Int16</span></span>|  
|<span data-ttu-id="74ef1-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="74ef1-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="74ef1-485">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-485">Int16</span></span>|  
|<span data-ttu-id="74ef1-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-486">REMARKS</span></span>|<span data-ttu-id="74ef1-487">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-487">String</span></span>|  
|<span data-ttu-id="74ef1-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="74ef1-489">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="74ef1-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="74ef1-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="74ef1-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-491">ColumnName</span></span>|<span data-ttu-id="74ef1-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="74ef1-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="74ef1-494">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-494">String</span></span>|  
|<span data-ttu-id="74ef1-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="74ef1-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="74ef1-496">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-496">String</span></span>|  
|<span data-ttu-id="74ef1-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="74ef1-498">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-498">String</span></span>|  
|<span data-ttu-id="74ef1-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-499">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-500">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-500">String</span></span>|  
|<span data-ttu-id="74ef1-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-501">COLUMN_TYPE</span></span>|<span data-ttu-id="74ef1-502">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-502">Int16</span></span>|  
|<span data-ttu-id="74ef1-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-503">DATA_TYPE</span></span>|<span data-ttu-id="74ef1-504">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-504">Int16</span></span>|  
|<span data-ttu-id="74ef1-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-505">TYPE_NAME</span></span>|<span data-ttu-id="74ef1-506">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-506">String</span></span>|  
|<span data-ttu-id="74ef1-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="74ef1-507">PRECISION</span></span>|<span data-ttu-id="74ef1-508">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-508">Int32</span></span>|  
|<span data-ttu-id="74ef1-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-509">LENGTH</span></span>|<span data-ttu-id="74ef1-510">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-510">Int32</span></span>|  
|<span data-ttu-id="74ef1-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="74ef1-511">SCALE</span></span>|<span data-ttu-id="74ef1-512">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-512">Int16</span></span>|  
|<span data-ttu-id="74ef1-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="74ef1-513">RADIX</span></span>|<span data-ttu-id="74ef1-514">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-514">Int16</span></span>|  
|<span data-ttu-id="74ef1-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-515">NULLABLE</span></span>|<span data-ttu-id="74ef1-516">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-516">Int16</span></span>|  
|<span data-ttu-id="74ef1-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-517">REMARKS</span></span>|<span data-ttu-id="74ef1-518">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-518">String</span></span>|  
|<span data-ttu-id="74ef1-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="74ef1-519">OVERLOAD</span></span>|<span data-ttu-id="74ef1-520">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-520">Int32</span></span>|  
|<span data-ttu-id="74ef1-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-522">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="74ef1-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="74ef1-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="74ef1-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="74ef1-524">ColumnName</span></span>|<span data-ttu-id="74ef1-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="74ef1-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="74ef1-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="74ef1-527">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-527">String</span></span>|  
|<span data-ttu-id="74ef1-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="74ef1-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="74ef1-529">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-529">String</span></span>|  
|<span data-ttu-id="74ef1-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="74ef1-531">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-531">String</span></span>|  
|<span data-ttu-id="74ef1-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-532">COLUMN_NAME</span></span>|<span data-ttu-id="74ef1-533">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-533">String</span></span>|  
|<span data-ttu-id="74ef1-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-534">COLUMN_TYPE</span></span>|<span data-ttu-id="74ef1-535">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-535">Int16</span></span>|  
|<span data-ttu-id="74ef1-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-536">DATA_TYPE</span></span>|<span data-ttu-id="74ef1-537">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-537">Int16</span></span>|  
|<span data-ttu-id="74ef1-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="74ef1-538">TYPE_NAME</span></span>|<span data-ttu-id="74ef1-539">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-539">String</span></span>|  
|<span data-ttu-id="74ef1-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="74ef1-540">COLUMN_SIZE</span></span>|<span data-ttu-id="74ef1-541">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-541">Int32</span></span>|  
|<span data-ttu-id="74ef1-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="74ef1-543">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-543">Int32</span></span>|  
|<span data-ttu-id="74ef1-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="74ef1-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="74ef1-545">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-545">Int16</span></span>|  
|<span data-ttu-id="74ef1-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="74ef1-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="74ef1-547">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-547">Int16</span></span>|  
|<span data-ttu-id="74ef1-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-548">NULLABLE</span></span>|<span data-ttu-id="74ef1-549">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-549">Int16</span></span>|  
|<span data-ttu-id="74ef1-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="74ef1-550">REMARKS</span></span>|<span data-ttu-id="74ef1-551">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-551">String</span></span>|  
|<span data-ttu-id="74ef1-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="74ef1-552">COLUMN_DEF</span></span>|<span data-ttu-id="74ef1-553">String</span><span class="sxs-lookup"><span data-stu-id="74ef1-553">String</span></span>|  
|<span data-ttu-id="74ef1-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="74ef1-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="74ef1-555">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-555">Int16</span></span>|  
|<span data-ttu-id="74ef1-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="74ef1-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="74ef1-557">Int16</span><span class="sxs-lookup"><span data-stu-id="74ef1-557">Int16</span></span>|  
|<span data-ttu-id="74ef1-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="74ef1-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="74ef1-559">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-559">Int32</span></span>|  
|<span data-ttu-id="74ef1-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="74ef1-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="74ef1-561">Int32</span><span class="sxs-lookup"><span data-stu-id="74ef1-561">Int32</span></span>|  
|<span data-ttu-id="74ef1-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="74ef1-562">IS_NULLABLE</span></span>|<span data-ttu-id="74ef1-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="74ef1-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74ef1-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74ef1-564">See Also</span></span>  
 [<span data-ttu-id="74ef1-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="74ef1-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
