function gfm(a) {
    "use strict";
    var start = Date.now();
    var end;
    var get_factor = function (a) {
        var is_prime = function (g) { // PRIME CHECK
            var limit;
            var mod = 2;
            var output = true;
            if (g >= 2 && g % Math.floor(g) === 0) {
                limit = Math.floor(Math.sqrt(g));
                while (mod <= limit) {
                    if (g % mod === 0) {
                        output = false;
                        break;
                    }
                    mod += 1;
                }
            } else {
                output = false;
            }
            return output;
        };

        var buffer = a;
        var factors_list = [];
        var multiples = [];
        var div = 2;
        var buff_mult = [];
        var divr = 2;
        var i = 0;

        var get_div = function () {
            while (buffer % div !== 0) {
                div += 1;
            }
        };

        var get_multiples = function () {
            while (divr <= Math.floor(Math.sqrt(a))) {
                if (a % divr === 0) {
                    buff_mult.push(divr);
                }
                divr += 1;
            }
            i = 0;
            while (i < buff_mult.length) {
                multiples.push(a / buff_mult[i]);
                i += 1;
            }
            multiples.reverse();
            buff_mult = buff_mult.concat(multiples);
        };

        var construct_multiples = function () {
            if (buff_mult.indexOf(1) < 0) {
                buff_mult.unshift(1);
            }
            if (buff_mult.indexOf(a) < 0) {
                buff_mult.push(a);
            }

            multiples = [];
            i = 0;
            while (i < buff_mult.length / 2) {
                multiples.push([buff_mult[i], buff_mult[buff_mult.length - i - 1]]);
                i += 1;
            }
        };

        var factorise = function () {
            while (buffer > 1) { // GET FACTORS
                get_div();
                if (is_prime(div)) {
                    buffer = buffer / div;
                    factors_list.push(div);
                }
            }
        };

        factorise();
        factors_list.unshift(1);

        if (factors_list.length <= 2) {
            buff_mult = factors_list.slice();
        } else {
            get_multiples();
        }

        if (buff_mult.length) {
            construct_multiples();
        }

        return [factors_list, multiples];
    };

    var limit = 1e9; // Limit input 1 billion
    var result = "Error: invalid input → must be a positive integer greater than 1 → max 1,000,000,000 (one billion)";
    if (a > 1 && a % 1 === 0 && a > 0 && a <= limit) {
        result = get_factor(a);
        result = {factors: result[0], multiples: result[1]};
    }
    if (result.constructor === Object) {
        end = Date.now();
        result.duration = (end - start) + " ms";
    }
    return result;
}
