pipeline{
    agent any
    options{
        timestamps()
        ansiColor('xterm')
        buildDiscarder(logRotator(numToKeepStr: '15'))
    }
    parameters{
        booleanParam(name: 'TOMS', defaultValue: false, description: '')
        text(name: 'toms_patches', defaultValue: "", description: 'TOMS Patches URLs.')
        string(name: 'toms_ai_args', defaultValue: "", description: 'AI flags to use for TOMS installation')
        booleanParam(name: 'TBAPI', defaultValue: false, description: '')
        text(name: 'tbapi_patches', defaultValue: "", description: 'TBAPI Patches URLs.')
        booleanParam(name: 'SSP_eCare', defaultValue: false, description: '')
        text(name: 'eCare_patches', defaultValue: "", description: 'eCare Patches URLs.')
        booleanParam(name: 'SSP_eCommerce', defaultValue: false, description: '')
        text(name: 'eCommerce_patches', defaultValue: "", description: 'eCommerce Patches URLs.')
        booleanParam(name: 'SSP_eContent', defaultValue: false, description: '')
        text(name: 'eContent_patches', defaultValue: "", description: 'eContent Patches URLs.')
        booleanParam(name: 'SSP_ePOS', defaultValue: false, description: '')
        text(name: 'ePOS_patches', defaultValue: "", description: 'ePOS Patches URLs.')
        booleanParam(name: 'RBM_with_flags', defaultValue: false, description: '')
        text(name: 'rbm_patches_with_flags', defaultValue: "", description: 'RBM Patches URLs.')
        booleanParam(name: 'RBM', defaultValue: false, description: '')
        text(name: 'rbm_patches', defaultValue: "", description: 'RBM Patches URLs.')
        booleanParam(name: 'CM', defaultValue: false, description: '')
        text(name: 'cm_patches', defaultValue: "", description: 'CM Patches URLs.')
        booleanParam(name: 'DOC1', defaultValue: false, description: '')
        text(name: 'doc1_patches', defaultValue: "", description: 'DOC1 Patches URLs.')
    }
}
