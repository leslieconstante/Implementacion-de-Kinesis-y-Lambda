# Implementacion-de-Kinesis-y-Lambda
Implementación usano Amazon Kinesis y Data Firehos
console.log('Loading function');

exports.handler = async (event, context) => {
    /* Process the list of records and transform them */
    const output = event.records.map((record) => ({
        /* This transformation is the "identity" transformation, the data is left intact */
        recordId: record.recordId,
        result: 'Ok',
        data: record.data,
    }));
    console.log(`Processing completed.  Successful records ${output.length}.`);
    return { records: output };
};
