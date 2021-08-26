<?php

$cpf = '603.887.110-19';

function validaCpf($cpf) {

    $digitoUm = 0;
    $digitoDois = 0;

    // Extrai somente os números
    $cpf = preg_replace('/[^0-9]/', '', $cpf);

    // Verifica se foi informado todos os digitos corretamente
    if (strlen($cpf) != 11) {
        return false;
    }

    // Verifica se foi informada uma sequência de digitos repetidos
    if (preg_match('/(\d)\1{10}/', $cpf)) {
        return false;
    }
    for($i=0, $x=10;$i<=8;$i++,$x--){
        $digitoUm+= $cpf[$i] * $x;
    }
    for($i=0,$x=11;$i<=9; $i++,$x--){
        $digitoDois += $cpf[$i] * $x;
    }

    $calculoUm = (($digitoUm % 11)<2) ? 0 : 11-($digitoUm% 11);
    $calculoDois = (($digitoDois % 11)<2) ? 0 : 11-($digitoDois% 11);

    if($calculoUm != $cpf[9] or $calculoDois != $cpf[10]){
        return false;
    }
    return true;
} 
    if (validaCpf($cpf)){
        echo "CPF valido!";
    } else echo "cpf invalido!";
